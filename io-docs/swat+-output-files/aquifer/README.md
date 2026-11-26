# Aquifer

Aquifer outputs describe groundwater storage, water-table depth, water exchanges, and nutrient transport. Output frequency is selected in `print.prt`; individual aquifer and basin outputs can be selected separately using the `aquifer` and `basin_aqu` lines, respectively. These map to the independent `pco%aqu` and `pco%aqu_bsn` controls.

The files are:

- Individual aquifers: `aquifer_day.txt`, `aquifer_mon.txt`, `aquifer_yr.txt`, and `aquifer_aa.txt`.
- Basin aggregates: `basin_aqu_day.txt`, `basin_aqu_mon.txt`, `basin_aqu_yr.txt`, and `basin_aqu_aa.txt`.

Set `csvout = y` to open the corresponding CSV files. The suffixes mean daily, monthly, yearly, and average annual. Daily rows follow the daily print window and interval. The basin files can be opened by the print settings even when the basin writer is skipped. The model calls that writer only when `db_mx%aqu_elem > 0`. [Aquifer controls](../../introduction-1/simulation-settings/print.prt/README.md), [basin dispatch](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L632-L636).

| Field | Description | Unit |
| --- | --- | --- |
| [jday](jday.md) | Day of year | n/a |
| [mon](mon.md) | Month | n/a |
| [day](day.md) | Day of month | n/a |
| [yr](yr.md) | Calendar year | n/a |
| [unit](unit.md) | Aquifer identifier; basin identifier for basin output | n/a |
| [gis_id](gis_id.md) | GIS identifier | n/a |
| [name](name.md) | Aquifer name or basin name | n/a |
| [flo](flo.md) | Groundwater flow leaving the aquifer | mm |
| [dep_wt](dep_wt.md) | Depth from the ground surface to the water table | m |
| [stor](stor.md) | Water stored in the aquifer | mm |
| [rchrg](rchrg.md) | Recharge entering the aquifer | mm |
| [seep](seep.md) | Seepage leaving the bottom of the aquifer | mm |
| [revap](revap.md) | Groundwater used for evaporation and plant uptake | mm |
| [no3_st](no3_st.md) | Nitrate nitrogen stored in the aquifer | kg N/ha |
| [minp](minp.md) | Calculated soluble-phosphorus load assigned to outflow by the 1-D controller | kg P in that calculation; see caveats |
| [orgn](orgn.md) | Aquifer carbon percentage under a mismatched nitrogen heading | percent |
| [orgp](orgp.md) | Organic-nitrogen component under a mismatched phosphorus heading | unresolved source unit |
| [no3_rchg](no3_rchg.md) | Nitrate nitrogen entering with recharge | kg N/ha |
| [no3_loss](no3_loss.md) | Nitrate removed by the first-order aquifer loss calculation | kg N/ha convention; see caveats |
| [no3_lat](no3_lat.md) | Nitrate nitrogen leaving with groundwater discharge | kg N/ha |
| [no3_seep](no3_seep.md) | Nitrate nitrogen leaving with seepage | kg N/ha |
| [flo_cha](flo_cha.md) | Groundwater flow routed to channels | mm |
| [flo_res](flo_res.md) | Groundwater flow routed to reservoirs | mm |
| [flo_ls](flo_ls.md) | Groundwater flow assigned to receiving aquifer objects | mm |

{% hint style="warning" %}
In the inspected main version, the columns headed `orgn` and `orgp` do not match the values written in those positions. They contain the aquifer carbon and organic-nitrogen values, respectively. The carbon value is initialized as percent, despite the printed nitrogen-mass unit. The organic-nitrogen component has conflicting source annotations and no direct update in the inspected 1-D controller. Retain the literal printed headings when reading files; do not reinterpret either as an organic-phosphorus output.
{% endhint %}

## Period and spatial treatment

The individual and basin TXT/CSV records all have 24 columns: seven identifiers and 17 numeric components. Daily rows contain the current component values. Monthly and yearly exchanges accumulate over the period; the three state fields `stor`, `dep_wt`, and `no3_st` instead use these rules:

- Monthly: daily sums divided by the calendar month's day count.
- Yearly: monthly means summed and divided by 12, giving equal weight to months rather than to days.
- Average annual: yearly means summed and divided by `time%yrs_prt`.

Both writers transfer monthly accumulators at calendar month end. If the run ends before that day, the final partial month contributes neither exchange totals nor state means to the yearly and average-annual rows. The yearly state calculation still divides by 12. [Individual accumulation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aquifer_output.f90#L29-L50), [basin accumulation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_aquifer_output.f90#L36-L57).

The same fixed month/year divisors apply at partial reporting boundaries. The two other constituent components, `minp` and the organic-nitrogen component printed under `orgp`, are summed over days instead of treated as mean storage. Carbon printed under `orgn` is copied through the period operators without summation or division ([individual writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aquifer_output.f90#L29); [basin writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_aquifer_output.f90#L36); [operators](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aquifer_module.f90#L175)).

Basin aggregation uses `aqu_prm(iaq)%area_ha / bsn%area_tot_ha`. The denominator is the full basin area, not the sum of aquifer areas, so this is not necessarily a normalized mean over aquifers. Carbon is an exception: the multiply operator leaves it unchanged and the add operator replaces it with its right-hand operand. Basin carbon therefore comes from the last aquifer in the aggregation loop, even if its area weight is zero ([aggregation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_aquifer_output.f90#L17); [addition](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aquifer_module.f90#L184); [multiplication](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aquifer_module.f90#L230)).

## Calculation and unit caveats

- `minp` is assigned `hin%flo * aqu_dat%minp / 1000` and copied to outgoing `solp`. Incoming water volume in m3 times the fixed concentration in mg/L gives kg P, with no division by aquifer area. This contradicts both the storage description and the printed kg/ha label. Basin weighting is still applied to this whole-aquifer load, so the basin value is neither a simple total load nor an area-normalized kg/ha value ([1-D assignment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L173)).
- `no3_st` is initialized from `10 * flo * area_ha * concentration / 1000`, producing kg, whereas the daily controller adds recharge divided by area and treats stored nitrate as kg N/ha. The nitrate fields retain the daily calculation's kg N/ha convention; this does not certify consistent mass accounting across initialization and all configurations ([initialization](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_initial.f90#L175); [daily calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L138)).
- Water-allocation paths also need care: canal seepage adds hydrograph water volume and nutrient masses directly to aquifer components without the area conversions used by the 1-D controller. Withdrawal scales these components and multiplies `minp` by area when constructing its outgoing hydrograph. Thus the units established for the ordinary 1-D assignments are not a claim that every allocation path uses the same mass basis ([canal additions](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_canal.f90#L33); [withdrawal](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_withdraw.f90#L111)).
- `dep_wt` is computed after recharge and any point-of-diversion allocation, before subtracting the day's groundwater flow, seepage, and revap. The reported water storage is subsequently changed. The printed depth and storage therefore do not necessarily represent the same point in the daily update sequence ([update sequence](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L97)).
- `flo_cha`, `flo_res`, and `flo_ls` include only outgoing connections with hydrograph type `tot`. They select channel (`cha`/`sdc`), reservoir (`res`), and aquifer (`aqu`) receivers, respectively. Despite its name, `flo_ls` does not select HRU or routing-unit receivers in this controller ([routing diagnostics](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L380)).

These caveats describe the pinned source's assignments and operators. Their numerical effects have not been tested with a model run.

## Initialization and water allocation

- **Initial storage uses the parameter-record index for depth.** The initializer copies the selected parameter record to aquifer object `iaq` and sets `aqu_d(iaq)%dep_wt`. The storage calculation then reads `aqu_d(iaqdb)%dep_wt`, where `iaqdb` is the parameter-record index and `aqu_d` is sized by aquifer objects. When the indices differ, the calculation can read another object's depth or an uninitialized object's zero default. A parameter index above the number of objects is outside the array bounds. The `sp_yld` calibration branch uses the current aquifer object's depth when it recalculates storage. [Initialization](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_initial.f90#L19-L24), [storage assignment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_initial.f90#L164-L174), [specific-yield calibration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L975-L980).
- **The withdrawal record uses storage after the withdrawal.** For a clamped withdrawal fraction `rto`, the aquifer allocation branch removes `rto` of the original water, nitrate, and mineral-P states. It builds the delivered hydrograph by multiplying the reduced states by `rto`. On a consistent unit basis, the delivered fraction of the original state is therefore `rto * (1 - rto)`. At `rto = 1`, the branch empties those states and reports zero delivery. The threshold check uses the existing `dep_wt` before the 1-D controller recalculates depth. [Withdrawal branch](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_withdraw.f90#L111-L124), [1-D update order](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L97-L107).
- **Canal seepage changes storage directly.** The canal path adds its seepage to `stor`, `no3_st`, and `minp`. It leaves `rchrg` unchanged. That column comes from the aquifer's incoming hydrograph, so it does not record the direct canal addition. [Canal writes](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_canal.f90#L33-L48), [recharge calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L76-L98).

## Calibration and reported values

For the 1-D aquifer, startup initializes the live aquifer state before applying the changes from `calibration.cal`. The effects below describe changes applied through that startup path. [Startup order](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/main.f90.in#L71-L73) · [Calibration setup](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/main.f90.in#L117-L121) · [Aquifer initialization](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/proc_aqu.f90#L8-L12) · [Parameter-change dispatch](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/proc_cal.f90#L13-L20)

| Calibration name | Effect on the aquifer and its output |
| --- | --- |
| `flo_init_mm`, `dep_wt_init`, `cbn_init` | Change the parameter record. The live starting flow, water-table depth, and carbon used by `flo`, `dep_wt`, and the column headed `orgn` were already copied and are not refreshed by these entries. |
| `dep_bot` | Changes the bottom depth used to calculate `dep_wt` in the daily controller. Changing it alone leaves initial `stor` unchanged. |
| `sp_yld` | Recalculates live storage immediately using the bottom depth then in the parameter record and the live water-table depth. If both `dep_bot` and `sp_yld` change, their order can change the starting storage. |
| `alpha`, `flo_min` | `alpha` updates the exponential factor used to blend previous baseflow and recharge. `flo_min` sets the maximum water-table depth at which that baseflow calculation runs. |
| `deep_seep` | Changes the fraction of recharge passed to the `seep` calculation, which caps the result at available storage. |
| `revap_co`, `revap_min` | Change the PET multiplier and the depth threshold for `revap`. Water-table depth must be strictly less than `revap_min`. |
| `no3_init`, `hlife_n` | `no3_init` recalculates the live nitrate state from the current flow and area, retaining the mass-basis caveat above. `hlife_n` updates the daily nitrate survival factor used to compute `no3_loss`. |
| `minp_init` | Changes the concentration used by the controller to compute daily `minp` from incoming water volume. The entry leaves the already initialized live mass alone until that daily assignment. |
| `bf_max` | Changes how calculated baseflow is distributed among linked channels when the aquifer-to-channel linkage is active. It does not cap the daily `flo` calculation. |
| `flo_dist` | Changes the stored flow-distance parameter. The 1-D controller does not read it. |

[All 15 aquifer calibration branches](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L928-L993) · [Calibration record order](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_conditions.f90#L48-L57) · [Initial state copies](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_initial.f90#L164-L178) · [Daily water and nutrient calculations](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L105-L175) · [Channel distribution](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L280-L303)
