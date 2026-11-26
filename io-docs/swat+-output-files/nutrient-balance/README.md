# Nutrient Balance
See the [HRU nutrient balance schema](hru.md) for the HRU-specific file layout and field pages.


Nutrient balance output can be printed at basin, LSU, and HRU level by entering "y" in the _basin\_nb_, _lsunit\_nb_, and _hru\_nb_ lines in [print.prt](../../introduction-1/simulation-settings/print.prt), respectively. Nutrient balance output can be printed at daily, monthly, yearly, and average annual time steps. The names of the nutrient balance output files are as follows:&#x20;

* basin\_nb\_day.txt
* basin\_nb\_mon.txt
* basin\_nb\_yr.txt
* basin\_nb\_aa.txt
* lsunit\_nb\_day.txt
* lsunit\_nb\_mon.txt
* lsunit\_nb\_yr.txt
* lsunit\_nb\_aa.txt
* hru\_nb\_day.txt
* hru\_nb\_mon.txt
* hru\_nb\_yr.txt
* hru\_nb\_aa.txt

Set `csvout` to `y` for the corresponding CSV files. Daily records also follow the shared daily print window and interval in `print.prt`. The monthly accumulators collect daily values independently of whether daily rows are written. [Daily print timing](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_control.f90#L194), [HRU accumulation and print gate](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_output.f90#L39)

All 24 variants print the same 28 headings and a 26-entry units record. The units record has seven blank identifiers followed by 19 entries labeled `kgha`. The final two headings, `plant_cov` and `mgt_ops`, have values in HRU rows. Basin and LSU rows end at `gwsoilp`, for 26 written values. The HRU TXT writer limits the object name to eight characters. [Heading and units declarations](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L360), [HRU TXT format](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_output.f90#L327)

| Field | Description | Unit |
| --- | --- | --- |
| [jday](jday.md) | Julian day | n/a |
| [mon](mon.md) | Month | n/a |
| [day](day.md) | Day of the month | n/a |
| [yr](yr.md) | Year | n/a |
| [unit](unit.md) | ID of the object | n/a |
| [gis_id](gis_id.md) | Object ID in GIS | n/a |
| [name](name.md) | Name of the object or SWAT+ setup (basin outputs) | n/a |
| [grzn](grzn.md) | Grazing manure nitrogen recorded by the static carbon routine | kg N/ha |
| [grzp](grzp.md) | Grazing manure phosphorus recorded by the static carbon routine | kg P/ha |
| [lab_min_p](lab_min_p.md) | Signed mineral-P exchange: positive labile to active; negative active to labile | kg P/ha |
| [act_sta_p](act_sta_p.md) | Signed mineral-P exchange: positive active to stable; negative stable to active | kg P/ha |
| [fertn](fertn.md) | Nitrogen in fertilizer and manure applications, including direct wetland fertilizer | kg N/ha |
| [fertp](fertp.md) | Phosphorus in fertilizer and manure applications, including direct wetland fertilizer | kg P/ha |
| [fixn](fixn.md) | Nitrogen added to plant biomass via fixation | kg/ha |
| [denit](denit.md) | Nitrogen lost from nitrate pool by denitrification | kg/ha |
| [act_nit_n](act_nit_n.md) | Nitrogen moving from active organic pool to nitrate pool | kg/ha |
| [act_sta_n](act_sta_n.md) | Signed transfer between active and stable organic N pools in the static carbon routine | kg N/ha |
| [org_lab_p](org_lab_p.md) | Phosphorus moving from the organic pool to labile pool | kg/ha |
| [rsd_nitorg_n](rsd_nitorg_n.md) | Residue nitrate mineralization diagnostic cleared before output | kg N/ha |
| [rsd_laborg_p](rsd_laborg_p.md) | Residue labile-P mineralization diagnostic cleared before output | kg P/ha |
| [no3atmo](no3atmo.md) | Nitrate nitrogen added to the soil by wet and dry atmospheric deposition | kg N/ha |
| [nh4atmo](nh4atmo.md) | Ammonium nitrogen added to the soil by wet and dry atmospheric deposition | kg N/ha |
| [nuptake](nuptake.md) | Plant nitrogen uptake | kg/ha |
| [puptake](puptake.md) | Plant phosphorus uptake | kg/ha |
| [gwsoiln](gwsoiln.md) | Nitrogen transferred from the aquifer to the soil by the GWFlow module | kg/ha |
| [gwsoilp](gwsoilp.md) | Phosphorus transferred from the aquifer to the soil by the GWFlow module | kg/ha |
| [plant_cov](plant_cov.md) | Plant-cover label written for HRU rows | n/a |
| [mgt_ops](mgt_ops.md) | Management-operation label written for HRU rows | n/a |

At source revision `6f515368`, standalone HRU-LTE nutrient-balance output is disabled: its open/header and data-write blocks are commented out in the [initialization routine](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_init.f90#L586) and [HRU-LTE output routine](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_output.f90#L30). A recognized `hru-lte_nb` print option does not establish that these files are produced.

## Where the daily values come from

- **Residue and organic pools.** In `cswat = 0`, `rsd_decomp` adds the 80% surface-residue mineral share to the two diagnostics, then `nut_nminrl` clears both before output. It supplies the signed `act_sta_n` and the `act_nit_n` and `org_lab_p` values. In `cswat = 2`, the residue routines clear the same diagnostics and the modern transformations do not refill those five legacy fields. `denit` is populated in both modes, by `nut_nminrl` or `cbn_zhang2`, respectively. [carbon mode dispatch](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L388-L411), [legacy clear and organic pool transfers](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/nut_nminrl.f90#L82-L146), [SWAT-C clear](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cbn_rsd_transfer.f90#L58-L64), [SWAT-C denitrification](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cbn_zhang2.f90#L438-L444).
- **Mineral P.** `lab_min_p` and `act_sta_p` are signed layer sums from `nut_pminrl` or the alternative `nut_pminrl2` when `sol_P_model = 1`. The alternative still sums the calculated transfers when total mineral P in a layer is at least 10,000 mg/kg and the pool updates are skipped. [model switch](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L407-L412), [default P pools and diagnostics](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/nut_pminrl.f90#L36-L59), [alternative P update guard](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/nut_pminrl2.f90#L149-L167).
- **Management inputs and plant uptake.** Grazing supplies `grzn` and `grzp`; on SWAT+ dev grazing manure is applied with the manure routine in both carbon modes, so it is also counted in `fertn` and `fertp`. Fertilizer, manure application, and direct wetland fertilizer all add to `fertn` and `fertp`. The nitrogen uptake routine adds fixation before recording `nuptake`. Both uptake routines clear their printed diagnostic on each plant call, so a later call with negligible demand can clear an earlier result. [daily reset](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/varinit.f90#L96-L100), [grazing manure](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_graze.f90#L89-L96), [fertilizer totals](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_fert.f90#L144-L147), [manure application totals](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_manure.f90#L179-L182), [wetland fertilizer totals](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_fert_wet.f90#L71-L77), [plant N uptake](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_nup.f90#L61-L100), [plant P uptake](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_pup.f90#L52-L81).
- **Groundwater inputs.** With GWFlow soil transfer and solutes enabled, `gwsoiln` and `gwsoilp` sum the layer transfers applied to soil nitrate and labile P, respectively. The output reports the deposited mass per HRU hectare in kg N/ha and kg P/ha. [layer transfer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_soil.f90#L108-L114), [N addition](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/nut_nlch.f90#L59-L66), [P addition](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/nut_solp.f90#L49-L56), [HRU nutrient assignment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L778-L785).

## Spatial and time aggregation

The individual HRU, landscape-unit, and basin writers omit a final partial month from yearly and average-annual nutrient totals. The daily sums move to the yearly record only at calendar month end, regardless of whether monthly printing is enabled. [HRU transfer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_output.f90#L100-L106), [landscape-unit transfer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lsu_output.f90#L104-L108), [basin transfer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_output.f90#L100-L104).

- **HRU.** The 19 numeric fields come from the HRU's daily nutrient record. The two trailing labels come from its land-use management record at the time of writing. [HRU writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_output.f90#L72)
- **LSU and basin.** Both have branches for full HRU and HRU-LTE records. The LSU writer indexes the daily record by element ID and uses `ru_frac` above `1.e-9`. The basin writer uses the selected object number to look up the daily record and `bsn_frac` above `1.e-12`. The weighting operator replaces each of the two residue mineralization values with zero when the input is below `1.e-10`. Basin rows write `1` for both `unit` and `gis_id`. [Contributor selection](../plant-and-weather/plant-weather-output.md#landscape-unit-and-basin-contributors), [Weighting operator](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L1254)
- **Reporting periods.** Monthly and yearly rows sum all 19 nutrient fields over the period. Average-annual rows divide the accumulated values by `time%yrs_prt`, the model's reporting-year divisor. The values are per year, although the units record still prints `kgha`. [HRU annual calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_output.f90#L263), [LSU annual calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lsu_output.f90#L231), [Basin annual calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_output.f90#L225), [Division operator](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L1229)
