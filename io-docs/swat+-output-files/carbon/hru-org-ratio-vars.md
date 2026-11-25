# HRU organic pool nitrogen-to-carbon ratios

Files `hru_org_ratio_vars.txt` and `hru_org_ratio_vars.csv` contain 13 columns. See [how to enable the reports](output-files-generated-by-hru_cb_vars.md). [Header](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_legacy_module.f90#L332), [Writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_carbvar_write_historical.f90#L78)

The three ratios follow the ten identifying columns. [Data type order](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_module.f90#L136)

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
| `ncbm` | Microbial biomass nitrogen-to-carbon ratio | kg N/kg C |
| `nchp` | Passive humus nitrogen-to-carbon ratio | kg N/kg C |
| `nchs` | Slow humus nitrogen-to-carbon ratio | kg N/kg C |

[Back to the hru_cb_vars reports](output-files-generated-by-hru_cb_vars.md).
