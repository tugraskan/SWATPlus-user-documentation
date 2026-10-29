# Management

`mgt_out.txt` records management operations as they are executed. The file uses one fixed header, but the meaning of `op_var` and `var1` through `var7` depends on the operation named in `operation`.

| Field | Description | Unit |
| --- | --- | --- |
| [hru](hru.md) | HRU identifier | n/a |
| [year](year.md), [mon](mon.md), [day](day.md) | Operation date | n/a |
| [crop/fert/pest](crop-per-fert-per-pest.md) | Crop, fertilizer, or pesticide name associated with the operation | n/a |
| [operation](operation.md) | Management operation name | n/a |
| [phubase](phubase.md), [phuplant](phuplant.md) | Base and plant heat-unit fractions | fraction |
| [soil_water](soil_water.md) | Soil-water state at the operation | mm |
| [plant_bioms](plant_bioms.md) | Plant biomass | kg/ha |
| [surf_rsd](surf_rsd.md) | Surface residue | kg/ha |
| [soil_no3](soil_no3.md) | Soil nitrate | kg/ha |
| [soil_solp](soil_solp.md) | Soil soluble phosphorus | kg/ha |
| [op_var](op_var.md) | Operation-specific variable label | n/a |
| [var1](var1.md), [var2](var2.md), [var3](var3.md), [var4](var4.md), [var5](var5.md), [var6](var6.md), [var7](var7.md) | Operation-specific values | operation-dependent |

`lu_change_out.txt` is a separate event report for land-use changes. Its fields and row content depend on the action being applied, so it should not be interpreted with the `mgt_out.txt` schema.
