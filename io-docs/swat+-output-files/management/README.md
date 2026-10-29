# Management

`mgt_out.txt` records management operations as they are executed. The file uses one fixed header, but the meaning of `op_var` and `var1` through `var7` depends on the operation named in `operation`.

| Field | Description | Unit |
| --- | --- | --- |
| [hru](hru.md) | HRU identifier | n/a |
| [year](year.md) | Calendar year | n/a |
| [mon](mon.md) | Month | n/a |
| [day](day.md) | Day of month | n/a |
| [crop/fert/pest](crop-per-fert-per-pest.md) | Crop, fertilizer, or pesticide name associated with the operation | n/a |
| [operation](operation.md) | Management operation name | n/a |
| [phubase](phubase.md) | Base heat-unit fraction | fraction |
| [phuplant](phuplant.md) | Plant heat-unit fraction | fraction |
| [soil_water](soil_water.md) | Soil-water state at the operation | mm |
| [plant_bioms](plant_bioms.md) | Plant biomass | kg/ha |
| [surf_rsd](surf_rsd.md) | Surface residue | kg/ha |
| [soil_no3](soil_no3.md) | Soil nitrate | kg/ha |
| [soil_solp](soil_solp.md) | Soil soluble phosphorus | kg/ha |
| [op_var](op_var.md) | Operation-specific variable label | n/a |
| [var1](var1.md) | Operation-specific value 1 | operation-dependent |
| [var2](var2.md) | Operation-specific value 2 | operation-dependent |
| [var3](var3.md) | Operation-specific value 3 | operation-dependent |
| [var4](var4.md) | Operation-specific value 4 | operation-dependent |
| [var5](var5.md) | Operation-specific value 5 | operation-dependent |
| [var6](var6.md) | Operation-specific value 6 | operation-dependent |
| [var7](var7.md) | Operation-specific value 7 | operation-dependent |

`lu_change_out.txt` is a separate event report for land-use changes. Its fields and row content depend on the action being applied, so it should not be interpreted with the `mgt_out.txt` schema.
