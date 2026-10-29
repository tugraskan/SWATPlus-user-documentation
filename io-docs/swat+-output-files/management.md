# Management

`mgt_out.txt` records management operations as they are executed. The file uses one fixed header, but the meaning of `op_var` and `var1` through `var7` depends on the operation named in `operation`.

| Field | Description | Unit |
| --- | --- | --- |
| [hru](management/hru.md) | HRU identifier | n/a |
| [year](management/year.md), [mon](management/mon.md), [day](management/day.md) | Operation date | n/a |
| [crop/fert/pest](management/crop-per-fert-per-pest.md) | Crop, fertilizer, or pesticide name associated with the operation | n/a |
| [operation](management/operation.md) | Management operation name | n/a |
| [phubase](management/phubase.md), [phuplant](management/phuplant.md) | Base and plant heat-unit fractions | fraction |
| [soil_water](management/soil_water.md) | Soil-water state at the operation | mm |
| [plant_bioms](management/plant_bioms.md) | Plant biomass | kg/ha |
| [surf_rsd](management/surf_rsd.md) | Surface residue | kg/ha |
| [soil_no3](management/soil_no3.md) | Soil nitrate | kg/ha |
| [soil_solp](management/soil_solp.md) | Soil soluble phosphorus | kg/ha |
| [op_var](management/op_var.md) | Operation-specific variable label | n/a |
| [var1](management/var1.md), [var2](management/var2.md), [var3](management/var3.md), [var4](management/var4.md), [var5](management/var5.md), [var6](management/var6.md), [var7](management/var7.md) | Operation-specific values | operation-dependent |

`lu_change_out.txt` is a separate event report for land-use changes. Its fields and row content depend on the action being applied, so it should not be interpreted with the `mgt_out.txt` schema.
