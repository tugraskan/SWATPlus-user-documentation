# Wetland

Wetland output is available at daily, monthly, yearly, and average-annual intervals as `wetland_day`, `wetland_mon`, `wetland_yr`, and `wetland_aa`, with `.txt` and `.csv` variants.

## How to produce these files

1. Assign a [wetland](../../introduction-1/wetlands/wetland.wet/README.md) to a full HRU through its surface-storage setting. SWAT+ writes wetland rows for full HRUs with a positive surface-storage index. [Wetland setup](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_initial.f90#L115), [Output caller](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L469)
2. In [print.prt](../../introduction-1/simulation-settings/print.prt/README.md), set the desired columns of the `reservoir` row to `y`. That row controls both reservoir and wetland output. The columns are daily, monthly, yearly, and average annual. For example, this setting enables daily wetland output. [Print row](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_print_codes_read.f90#L561), [File creation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_wetland.f90#L11)

```text
reservoir    y    n    n    n
```

Set `csvout` to `y` to also create the CSV files. For daily rows, check the reporting dates, print interval, and skipped years in `print.prt`. SWAT+ can create the files with headers even when the model has no wetland HRUs to write. [File creation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_wetland.f90#L11), [Daily writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wetland_output.f90#L18), [Skipped-year gate](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L439)

For wetland chemistry files, see the separate controls for [salt](../salt-outputs/README.md#how-to-produce-these-files) and [conservative constituents](../conservative-constituents/README.md#how-to-produce-these-files).

The wetland files share the printed schema used by reservoir output: the identifying columns `jday`, `mon`, `day`, `yr`, `unit`, `gis_id`, and `name`; the state columns `area`, `precip`, `evap`, `seep`, and `flo_stor`; then stored, incoming, and outgoing constituent blocks.

| Field | Description | Unit |
| --- | --- | --- |
| [jday](jday.md) | Day of year | n/a |
| [mon](mon.md) | Month | n/a |
| [day](day.md) | Day of month | n/a |
| [yr](yr.md) | Calendar year | n/a |
| [unit](unit.md) | HRU identifier | n/a |
| [gis_id](gis_id.md) | GIS identifier | n/a |
| [name](name.md) | HRU object name | n/a |
| [area](area.md) | Wetland surface area | ha |
| [precip](precip.md) | Precipitation volume | m3 |
| [evap](evap.md) | Evaporation volume | m3 |
| [seep](seep.md) | Seepage volume | m3 |
| [flo_stor](flo_stor.md) | Water stored in the wetland | m3 |
| [sed_stor](sed_stor.md) | Stored sediment | tons |
| [orgn_stor](orgn_stor.md) | Stored organic nitrogen | kg N |
| [sedp_stor](sedp_stor.md) | Stored sediment-associated phosphorus | kg P |
| [no3_stor](no3_stor.md) | Stored nitrate nitrogen | kg N |
| [solp_stor](solp_stor.md) | Stored soluble phosphorus | kg P |
| [chla_stor](chla_stor.md) | Stored chlorophyll a | kg |
| [nh3_stor](nh3_stor.md) | Stored ammonia | kg N |
| [no2_stor](no2_stor.md) | Stored nitrite | kg N |
| [cbod_stor](cbod_stor.md) | Stored carbonaceous biochemical oxygen demand | kg |
| [dox_stor](dox_stor.md) | Stored dissolved oxygen | kg |
| [san_stor](san_stor.md) | Stored sand | tons |
| [sil_stor](sil_stor.md) | Stored silt | tons |
| [cla_stor](cla_stor.md) | Stored clay | tons |
| [sag_stor](sag_stor.md) | Stored small aggregates | tons |
| [lag_stor](lag_stor.md) | Stored large aggregates | tons |
| [grv_stor](grv_stor.md) | Stored gravel | tons |
| [null](null.md) | Numeric temperature slot for the storage block; printed heading is `null` | not printed |
| [flo_in](flo_in.md) | Incoming water volume | m3 |
| [sed_in](sed_in.md) | Incoming sediment | tons |
| [orgn_in](orgn_in.md) | Incoming organic nitrogen | kg N |
| [sedp_in](sedp_in.md) | Incoming sediment-associated phosphorus | kg P |
| [no3_in](no3_in.md) | Incoming nitrate nitrogen | kg N |
| [solp_in](solp_in.md) | Incoming soluble phosphorus | kg P |
| [chla_in](chla_in.md) | Incoming chlorophyll a | kg |
| [nh3_in](nh3_in.md) | Incoming ammonia | kg N |
| [no2_in](no2_in.md) | Incoming nitrite | kg N |
| [cbod_in](cbod_in.md) | Incoming carbonaceous biochemical oxygen demand | kg |
| [dox_in](dox_in.md) | Incoming dissolved oxygen | kg |
| [san_in](san_in.md) | Incoming sand | tons |
| [sil_in](sil_in.md) | Incoming silt | tons |
| [cla_in](cla_in.md) | Incoming clay | tons |
| [sag_in](sag_in.md) | Incoming small aggregates | tons |
| [lag_in](lag_in.md) | Incoming large aggregates | tons |
| [grv_in](grv_in.md) | Incoming gravel | tons |
| [null](null.md) | Numeric temperature slot for the inflow block; printed heading is `null` | not printed |
| [flo_out](flo_out.md) | Outgoing water volume | m3 |
| [sed_out](sed_out.md) | Bulk sediment in the release after settling or flushing | tons |
| [orgn_out](orgn_out.md) | Outgoing organic nitrogen | kg N |
| [sedp_out](sedp_out.md) | Outgoing sediment-associated phosphorus | kg P |
| [no3_out](no3_out.md) | Outgoing nitrate nitrogen | kg N |
| [solp_out](solp_out.md) | Outgoing soluble phosphorus | kg P |
| [chla_out](chla_out.md) | Outgoing chlorophyll a | kg |
| [nh3_out](nh3_out.md) | Outgoing ammonia | kg N |
| [no2_out](no2_out.md) | Outgoing nitrite | kg N |
| [cbod_out](cbod_out.md) | Carbonaceous biochemical oxygen demand slot, left at zero by the wetland controller | kg |
| [dox_out](dox_out.md) | Dissolved oxygen slot, left at zero by the wetland controller | kg |
| [san_out](san_out.md) | Sand outflow slot, left at zero by the wetland controller | tons |
| [sil_out](sil_out.md) | Silt outflow slot, left at zero by the wetland controller | tons |
| [cla_out](cla_out.md) | Clay outflow slot, left at zero by the wetland controller | tons |
| [sag_out](sag_out.md) | Small aggregates outflow slot, left at zero by the wetland controller | tons |
| [lag_out](lag_out.md) | Large aggregates outflow slot, left at zero by the wetland controller | tons |
| [grv_out](grv_out.md) | Gravel outflow slot, left at zero by the wetland controller | tons |
| [null](null.md) | Numeric temperature slot for the outflow block; printed heading is `null` | not printed |

## How to read the reporting periods

All eight wetland files have 65 headings and 65 data values. The three `null` headings at positions 29, 47, and 65 correspond to numeric temperature components. Their printed unit entries are blank. [Header writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_wetland.f90#L15), [Data writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wetland_output.f90#L20), [Temperature declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L49)

| Fields | Daily | Monthly | Yearly | Average annual |
| --- | --- | --- | --- | --- |
| `area` | Daily area in ha | Sum of daily areas divided by calendar month length | Sum of monthly mean areas | Sum of yearly area values divided by the number of printed years |
| `precip`, `evap`, `seep` | Daily volume in m3 | Monthly totals | Yearly totals | Yearly totals summed and divided by the number of printed years |
| `flo_in`, `flo_out` | Daily volume in m3 | Monthly total divided by calendar month length, giving mean daily volume | Yearly totals | Yearly totals summed and divided by the number of printed years |
| Inflow and outflow constituent masses | Daily masses | Monthly totals | Yearly totals | Yearly totals summed and divided by the number of printed years |
| Storage block | Current state | Current state | Current state | Current state at simulation end |

The writer omits a final partial month from the yearly and average-annual area and flux accumulators. The storage block still shows the final-day snapshot. [Wetland accumulation and writes](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wetland_output.f90#L29-L87).

The yearly area is a sum of monthly means. For example, twelve monthly means of 2 ha give a yearly `area` of 24 in this source revision. The average-annual area inherits that calculation. For inflow and outflow, the writer adds the full monthly volumes to the yearly totals before dividing the monthly values for display. Hydrograph addition weights temperatures by water volume, and the average-annual division leaves them unchanged. These operations describe the reported values. The source trace does not establish meaningful wetland temperatures. [Monthly calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wetland_output.f90#L37), [Yearly and average-annual calculations](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wetland_output.f90#L59), [Area and volume operators](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_body_module.f90#L73), [Temperature weighting](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1337)

## What the nutrient blocks include

- **Inflow.** The wetland report includes routed surface runon and its associated tile flow when incoming surface volume exceeds `1.e-6` m³. It can also include floodplain inflow from a linked channel and, with GWFlow solute simulation enabled, groundwater nitrate and soluble phosphorus. The controller adds irrigation nitrate directly to stored nitrate and omits that addition from `no3_in`. [HRU runon](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L270-L282), [channel floodplain input](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L180-L199), [GWFlow input](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_wetland.f90#L137-L148), [irrigation and inflow writes](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wetland_control.f90#L79-L81).
- **Seepage.** The controller removes nitrate, ammonia, organic nitrogen, soluble phosphorus, and sediment-associated phosphorus from ponded water and transfers those masses to the top soil layer. The table's `seep` field is water volume in m³. The nutrient masses transferred by seepage have no columns in this table. [Seepage mass calculations](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wetland_control.f90#L141-L165).
- **Outflow and storage.** After water release is calculated, the shared nutrient routine applies settling to the remaining nutrient masses. It calculates each outgoing mass using the fraction `outflow volume / (remaining volume + outflow volume)` and subtracts that mass from storage. On SWAT+ dev the fraction is used only when the total volume exceeds `1.e-6` m³ and the outflow is at least `1.e-6` m³; otherwise the nutrient outflow is zero, and masses below `1.e-30` kg are set to zero first. If remaining volume is below `1.e-6` m³, the routine clears the stored record and returns before assigning nutrient outflow, even if the water-release volume is positive. [Wetland release and nutrient call](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wetland_control.f90#L178-L219), [low-volume guard](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_nutrient.f90#L33-L38), [settling and export](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_nutrient.f90#L70-L147).
- **Chlorophyll and oxygen.** The active chlorophyll calculation uses a phosphorus threshold and then a fixed mass per volume. The older concentration-dependent formula is commented out. The wetland controller initializes the outflow hydrograph to zero and leaves its CBOD and dissolved oxygen fields at zero. [Chlorophyll calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_nutrient.f90#L99-L108), [outflow initialization](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wetland_control.f90#L59-L64), [export assignments](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_nutrient.f90#L119-L137).

The three nutrient blocks therefore capture only part of the wetland nutrient balance.

Overbank and GWFlow inflows can add to the daily record during skipped years. The writer clears that record only in reporting years, so the first reporting day can include inflow accumulated during warm-up. [Overbank inflow](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L181-L199), [GWFlow inflow](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_wetland.f90#L137-L148), [Reporting gate](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L441-L474), [Daily reset](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wetland_output.f90#L29-L33)

## Sediment and particle sizes

The inflow block records bulk sediment and all six size classes from routed surface runon and accompanying tile flow when the HRU receives more than `1.e-6` m³ of surface runon. Linked channels can also supply sediment with overbank water. The storage block starts from the wetland's organic and mineral initialization record (the zero set on SWAT+ dev when there are no `om_water.ini` sets). A paddy puddling operation can replace the stored bulk sediment using the configured concentration and current water volume. [HRU runon](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L270-L278), [Overbank inflow](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L181-L199), [Wetland initialization](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_initial.f90#L151-L156), [Puddling operation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L591-L603)

The model calculates water release before it processes sediment. If the remaining volume is below `1.e-6` m³, the sediment routine clears the storage hydrograph and sets bulk sediment outflow to zero. Otherwise it calculates bulk sediment concentration from the remaining water volume. Above the equilibrium concentration `nsed`, it applies the settling coefficient derived from `d50`, calculates bulk export from the resulting concentration and release volume, and subtracts that export from the stored mass with a floor of zero. It also clears all six stored size classes. At or below `nsed`, the settling branch leaves those fields as they were. On SWAT+ dev bulk export is computed in both cases, as the concentration times the release volume capped at the stored mass, and subtracted from storage; flushing can replace that load. (On SWAT+ main, export stayed zero at or below `nsed` unless flushing supplied a load.) All six reported outflow size classes stay zero throughout these paths. [Settling parameters](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_initial.f90#L95-L101), [Release before settling](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wetland_control.f90#L179-L210), [Sediment routine](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_sediment.f90#L17-L61)

If the wetland starts the day below 0.0001 m of water depth and releases water, the flushing calculation replaces the stored bulk sediment and the outgoing bulk sediment from the settling calculation. The wetland's `sed_out` records that flush mass once. The HRU sediment-yield calculation adds it twice because the controller uses it in both terms. [Flush and HRU sediment yield](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wetland_control.f90#L227-L259), [Daily wetland report record](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wetland_control.f90#L270-L278)

## Oxygen and temperature values

Stored CBOD and dissolved oxygen accumulate from initialization and incoming hydrographs until a reset clears them. The wetland release routine keeps the outgoing masses at zero. Inflow temperature comes from incoming hydrographs. Storage temperature starts from the initialization record and is volume-weighted when hydrographs are added. Direct additions such as precipitation and GWFlow inflow change volume without adding a temperature. The temperature slot for wetland outflow stays zero because the controller starts with a zero release record and leaves its temperature unset. [Initialization conversion](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1285-L1306), [Hydrograph addition](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1337-L1363), [Outflow initialization and precipitation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wetland_control.f90#L59-L77), [GWFlow inflow](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_wetland.f90#L137-L148), [Low-volume reset](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_sediment.f90#L17-L24), [Export assignments](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_nutrient.f90#L119-L137)
