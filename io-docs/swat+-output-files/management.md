# Management

`mgt_out.txt` records management operations as they are executed. The file uses one fixed header, but the meaning of `op_var` and `var1` through `var7` depends on the operation named in `operation`.

| Field | Description | Unit |
| --- | --- | --- |
| hru | HRU identifier | n/a |
| year, mon, day | Operation date | n/a |
| crop/fert/pest | Crop, fertilizer, or pesticide name associated with the operation | n/a |
| operation | Management operation name | n/a |
| phubase, phuplant | Base and plant heat-unit fractions | fraction |
| soil_water | Soil-water state at the operation | mm |
| plant_bioms | Plant biomass | kg/ha |
| surf_rsd | Surface residue | kg/ha |
| soil_no3 | Soil nitrate | kg/ha |
| soil_solp | Soil soluble phosphorus | kg/ha |
| op_var | Operation-specific variable label | n/a |
| var1, var2, var3, var4, var5, var6, var7 | Operation-specific values | operation-dependent |

`lu_change_out.txt` is a separate event report for land-use changes. Its fields and row content depend on the action being applied, so it should not be interpreted with the `mgt_out.txt` schema.
