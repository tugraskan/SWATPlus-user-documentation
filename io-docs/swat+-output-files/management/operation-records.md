# Management operation records

All of these records share `mgt_out.txt`. See [Management](README.md) for the print setting and the file's nominal 21-column header. The first six values are the HRU, year, month, day, operation-specific name or option, and operation label. Labels such as `PADDY IRRIGATION` contain spaces. The counts below refer to values in the write list, with a whole residue record expanded to four values. [File opener](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_mgt.f90#L7), [Decision-table actions](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L156), [Scheduled actions](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L112)

## Rows with the full state prefix

The first 13 values follow the nominal header. The table lists the remaining values in order, starting at `op_var`. A dash means the writer ends the row at the state prefix. [Decision-table writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L379), [Scheduled writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L353)

| Operation and path | Values | After the state prefix, in order |
| --- | ---: | --- |
| `IRRIGATE`, standard decision-table irrigation or water allocation | 14 | Applied irrigation (mm) |
| `IRRIGATE`, scheduled irrigation | 15 | Applied irrigation, irrigation runoff (mm) |
| `IRRIG_trn` | 14 | Requested irrigation amount from `irr.ops` (mm) |
| `FERT`, `FERT-WET`, `MANURE`, `MANU` | 19 | Applied fertilizer or manure, nitrate N, ammoniacal N, organic N, soluble P, organic P (kg/ha) |
| `PEST` | 14 | Applied pesticide (kg/ha) |
| `TILLAGE` | 14 | Mixing efficiency (fraction) |
| `PLANT`, `TRANSPLANT`, `PLANT_ALREADY_GROWING` | 15 | Current leaf area index, potential leaf area index |
| `HARVEST`, `KILL`, `HARV/KILL` | 19 | Yield value (kg/ha), then accumulated nitrogen, phosphorus, temperature, water, and aeration stress |
| `GRAZE`, scheduled | 15 | Configured daily biomass removal and manure deposition (kg/ha/day) |
| `CNUP`, decision table | 15 | Previous curve number, updated curve number |
| `CNUP`, scheduled | 15 | Operation input `op3`, updated curve number |
| `DRAIN_CONTROL` | 14 | Controlled drain depth (mm) |
| `BEGIN_PADDY_IRRIGATION`, scheduled command | 15 | Raw schedule fields `op3`, `op4` |
| `BURN`, `STREET_SWEEP` | 13 | — |

For fertilizer rows, the five nutrient values occupy `var1` through `var5`. For harvest and kill rows, those same positions hold the five stress sums. The writers leave `var6` and `var7` unwritten on these rows. Decision-table `KILL` uses the local `yield` variable, while scheduled `KILL` writes `pl_yield%m`. [Fertilizer writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L379), [Decision-table kill writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L617), [Scheduled kill writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L254), [Stress declarations](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_module.f90#L80)

The decision-table planting branch can log both `PLANT` and `TRANSPLANT` for one event. The `TRANSPLANT` write checks `mgtout` even when the transplant call is skipped. Scheduled `DRAIN_CONTROL` indexes plant state and biomass by the HRU number (`j`), so those two state positions can select the wrong plant or be out of range. [Planting branch](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L478), [Scheduled drain writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L501)

## Abbreviated and expanded rows

| Operation and path | Values | What follows the first six values |
| --- | ---: | --- |
| `IMPOUND OFF`, `IMPOUND ON`, `PUDDLE` | 6 | Nothing |
| `PADDY IRRIGATION`, decision-table ponding | 7 | Applied irrigation (mm) |
| `BEGIN/ADJUST PADDY IRRIGATION`, `STOP PADDY IRRIGATION` | 7 | Maximum ponding depth (mm) |
| `RESET WEIR HEIGHT (m)` | 7 | Wetland weir height (m) |
| `IRRIGATE`, alternate decision-table branch | 17 | State values through plant biomass, then residue mass, C, N, and P, soil nitrate, soil soluble P, and applied irrigation |

The seventh value in a short paddy or weir record appears where the header lists `phubase`. For a decision-table reservoir weir action, the routine changes `res_ob(j)%weir_hgt` but the log still reads `wet_ob(j)%weir_hgt`. In the 17-value irrigation row, the last three positions are soil nitrate under `var1`, soil soluble P under `var2`, and applied irrigation under `var3`. [Short and expanded irrigation writes](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L347), [Weir action](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L939), [Scheduled paddy actions](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L529), [Residue component order](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/organic_mineral_mass_module.f90#L7)

[Back to Management](README.md).
