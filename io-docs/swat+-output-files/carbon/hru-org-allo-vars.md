# HRU decomposition allocation fractions

Files `hru_org_allo_vars.txt` and `hru_org_allo_vars.csv` contain 16 columns. See [how to enable the reports](output-files-generated-by-hru_cb_vars.md). [Header](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_legacy_module.f90#L312), [Writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_carbvar_write_historical.f90#L67)

All six allocation values appear under different headings. Read the values by position using the table below. The allocation values are dimensionless fractions. [Data type order](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_module.f90#L86), [Respiration fractions in use](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cbn_zhang2.f90#L762)

| Printed heading | Value written | Description |
| --- | --- | --- |
| `freq` | `freq` | Reporting event (`day`, `mon`, or `year`) |
| `soil_lyr` | `soil_lyr` | Soil layer number |
| `soil_depth` | `soil_depth` | Integer depth to the bottom of the layer (mm) |
| `jday` | `jday` | Day of year |
| `mon` | `mon` | Month |
| `day` | `day` | Day of month |
| `yr` | `yr` | Calendar year |
| `unit` | `unit` | HRU number |
| `gis_id` | `gis_id` | HRU GIS identifier |
| `name` | `name` | HRU name |
| `asp` | `abp` | Fraction of decomposed microbial biomass carbon allocated to passive humus |
| `abp` | `asp` | Fraction of decomposed slow humus carbon allocated to passive humus |
| `abco2` | `a1co2` | Respired fraction of decomposed metabolic and non-lignin structural litter carbon |
| `a1co2` | `asco2` | Respired fraction of decomposed slow humus carbon |
| `asco2` | `apco2` | Respired fraction of decomposed passive humus carbon |
| `apco2` | `abco2` | Respired fraction of decomposed microbial biomass carbon |

[Back to the hru_cb_vars reports](output-files-generated-by-hru_cb_vars.md).
