# HRU potential organic transformations

Files `hru_org_trans_vars.txt` and `hru_org_trans_vars.csv` contain 22 columns. See [how to enable the reports](output-files-generated-by-hru_cb_vars.md). [Header](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_legacy_module.f90#L349), [Writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_carbvar_write_historical.f90#L89)

The units row prints `kg/ha` for each of the twelve transformation columns. The source declares them as daily potentials in kg/ha/day. Monthly and yearly rows show the diagnostic on the reporting day. [Printed units](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_legacy_module.f90#L375), [Data type and daily units](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_module.f90#L151)

| Field | Description | Unit |
| --- | --- | --- |
| `freq` | Reporting event (`day`, `mon`, or `year`) | — |
| `soil_lyr` | Soil layer number | — |
| `soil_depth` | Integer depth to the bottom of the layer | mm |
| `jday` | Day of year | — |
| `mon` | Month | — |
| `day` | Day of month | — |
| `yr` | Calendar year | — |
| `unit` | HRU number | — |
| `gis_id` | HRU GIS identifier | — |
| `name` | HRU name | — |
| `bmctp` | Microbial biomass carbon | kg/ha |
| `bmntp` | Microbial biomass nitrogen | kg/ha |
| `hsctp` | Slow humus carbon | kg/ha |
| `hsntp` | Slow humus nitrogen | kg/ha |
| `hpctp` | Passive humus carbon | kg/ha |
| `hpntp` | Passive humus nitrogen | kg/ha |
| `lmctp` | Metabolic litter carbon | kg/ha |
| `lmntp` | Metabolic litter nitrogen | kg/ha |
| `lsctp` | Structural litter carbon | kg/ha |
| `lslctp` | Lignin carbon in structural litter | kg/ha |
| `lslnctp` | Non-lignin carbon in structural litter | kg/ha |
| `lsntp` | Structural litter nitrogen | kg/ha |

[Back to the hru_cb_vars reports](output-files-generated-by-hru_cb_vars.md).
