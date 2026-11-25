# Basin salt balance

The files are `basin_salt_day.txt`, `basin_salt_mon.txt`, `basin_salt_yr.txt`, and `basin_salt_aa.txt`. This report is TXT only.

## How to produce these files

Configure salts and set all four periods on the `basin_salt` row of [print.prt](../../introduction-1/simulation-settings/print.prt/README.md). The file opener checks those switches. The writer targets all four output units on their reporting dates regardless of the switches, so enabling all four ensures each unit has its named file. The writer runs after the skipped years and writes daily rows without a separate day window or interval. [File opener](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_salt.f90#L16), [Output caller](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L440), [Basin writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_balance.f90#L369)

## Column order

The report has 31 columns. The first three are `yr`, `mo`, and `jday`. The remaining columns are basin totals across the configured ions or across the mineral pools used in the calculation. [Header declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_module.f90#L75)

| Field | Description | Unit |
| --- | --- | --- |
| [`lat_kg`](lat_kg.md) | Salt reaching streams through lateral flow | kg |
| [`gw_kg`](gw_kg.md) | Standard aquifer discharge or signed GWFlow exchange plus saturation-excess return | kg |
| [`sur_kg`](sur_kg.md) | Salt in HRU soil surface runoff | kg |
| [`urb_kg`](urb_kg.md) | Urban runoff salt diagnostic, zero on this revision | kg |
| [`wet_kg`](wet_kg.md) | Salt in wetland runoff after the HRU runoff lag | kg |
| [`tile_kg`](tile_kg.md) | HRU tile drainage salt plus GWFlow tile drainage salt when enabled | kg |
| [`perc_kg`](perc_kg.md) | Salt transferred by percolation | kg |
| [`gwup_kg`](gwup_kg.md) | Salt transferred from groundwater to soil | kg |
| [`wtsp_kg`](wtsp_kg.md) | Salt transferred by wetland seepage | kg |
| [`irsw_kg`](irsw_kg.md) | Surface-water irrigation salt diagnostic, zero on this revision | kg |
| [`irgw_kg`](irgw_kg.md) | Groundwater irrigation salt diagnostic, zero on this revision | kg |
| [`irwo_kg`](irwo_kg.md) | Outside-source irrigation salt diagnostic, zero on this revision | kg |
| [`rain_kg`](rain_kg.md) | Salt added by rain | kg |
| [`dryd_kg`](dryd_kg.md) | Salt added by dry deposition | kg |
| [`road_kg`](road_kg.md) | Salt added by road-salt application | kg |
| [`fert_kg`](fert_kg.md) | Salt added by fertilizer | kg |
| [`amnd_kg`](amnd_kg.md) | Salt added by amendments | kg |
| [`uptk_kg`](uptk_kg.md) | Salt removed by plant uptake | kg |
| [`ptso_kg`](ptso_kg.md) | Salt entering the stream network from point sources within the watershed | kg |
| [`ptout_kg`](ptout_kg.md) | Salt entering the stream network from point sources outside the watershed | kg |
| [`rchg_kg`](rchg_kg.md) | Salt entering aquifers with recharge | kg |
| [`seep_kg`](seep_kg.md) | Salt leaving standard aquifer objects through seepage | kg |
| [`dssl_kg`](dssl_kg.md) | Net change in dissolved soil salt from mineral reactions | kg |
| [`dsaq_kg`](dsaq_kg.md) | Net change in dissolved groundwater salt from mineral reactions | kg |
| [`soilds_kg`](soilds_kg.md) | Dissolved salt stored in soils | kg |
| [`soilmn_kg`](soilmn_kg.md) | Mineral salt stored in soils | kg |
| [`aquds_kg`](aquds_kg.md) | Dissolved salt stored in aquifers | kg |
| [`aqumn_kg`](aqumn_kg.md) | Mineral salt stored in aquifers | kg |

## Daily values

The basin report reads the full-HRU diagnostics directly, multiplies each by the HRU's area in hectares, and sums across HRUs and ions. It reports soil surface runoff, urban runoff, and lagged wetland runoff separately. The groundwater-to-soil field reads the HRU groundwater transfer diagnostic even though the corresponding group is omitted from the HRU salt data rows. The three irrigation diagnostics have no active salt producer on this revision. Daily values below 0.000001 kg are set to zero for road salt, fertilizer, amendments, and plant uptake. The reporting-year gate also delays the daily reset of HRU input diagnostics, so fertilizer and uptake can include skipped-year additions on the first reported day. [Basin HRU calculations](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_balance.f90#L72-L227), [HRU salt diagnostics](../hru-salt/README.md), [Basin output and reset](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L612-L653)

With GWFlow enabled, groundwater loading combines signed groundwater-to-stream and stream-to-groundwater exchange with saturation-excess return, and the tile column includes both GWFlow cell drainage and HRU tile drainage. Groundwater loading, recharge, aquifer dissolution, and dissolved groundwater storage use GWFlow cell diagnostics when solute transport is enabled, and are zero when GWFlow runs with solute transport disabled. Aquifer seepage and solid aquifer salt always use the standard aquifer objects. [Groundwater and tile calculations](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_balance.f90#L49-L115), [Recharge, seepage, and dissolution](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_balance.f90#L247-L303), [Groundwater storage](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_balance.f90#L331-L367)

Soil dissolution is the area-scaled net change in dissolved salt from soil chemistry. Dissolved soil storage sums all soil layers and configured ions. Solid soil storage sums five mineral pools using each layer's thickness and bulk density. Solid aquifer storage uses five mineral pools and assumes 15 m of aquifer thickness and a bulk density of 2,000 kg/m³. [Soil dissolution and storage](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_balance.f90#L279-L329), [Solid aquifer storage](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_balance.f90#L354-L367)

## Reporting periods

The writer adds each eligible daily record directly to the monthly, yearly, and average-annual accumulators. Yearly and average-annual results therefore include a final partial month even though that month produces no separate monthly row. [Daily additions and period writes](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_balance.f90#L369-L411).

Monthly and yearly rows sum the first 24 salt fields. The last four fields (`soilds_kg`, `soilmn_kg`, `aquds_kg`, and `aqumn_kg`) are sums of daily stored mass divided by the day of the month or `time%day_end_yr`, respectively. In the average-annual file, the first 23 salt fields divide their daily sums by the configured number of simulation years (`time%nbyr`). The four storage fields divide by the number of included simulation days (`time%days_prt`). [Period calculations](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_balance.f90#L372), [Included day count](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_control.f90#L134)

The remaining field, `dsaq_kg`, is the cumulative aquifer mineral dissolution mass in kg for the included reporting years. The average-annual TXT preamble labels it kg/yr. [Average-annual preamble](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_salt.f90#L175), [Average-annual writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_balance.f90#L401)

[Back to the Salt Outputs index](README.md).
