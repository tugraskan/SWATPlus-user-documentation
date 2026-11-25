# Legacy HRU soil carbon pools

Files `hru_cpool_stat.txt` and `hru_cpool_stat.csv` use the named `hru_cb` row in [print.prt](../../introduction-1/simulation-settings/print.prt/README.md). Set `carbon = 2` in [codes.bsn](../../introduction-1/basin-1/codes.bsn/README.md) and use lowercase `l` for at least one requested period to enable the diagnostics. Enabled periods use `y` for profile rows and `l` for profile and layer rows. Set `csvout` to `y` for the CSV copy. Daily, monthly, and yearly events share the file. Rows show values on the reporting date. [File opener](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_legacy_module.f90#L472), [Reporting calls](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/command.f90#L525), [Data writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_write_historical.f90#L370)

The 22 columns include carbon pools, live root mass, and `soil_water`. In a layer row, `soil_water` is the layer's total water fraction including water at wilting point. In a profile row, the writer adds those layer fractions and divides by total profile thickness in mm. The units row prints `mm/mm` for both. The profile calculation uses a sum of fractions without weighting each one by layer thickness. [Layer water calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L499), [Profile water calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_write_historical.f90#L371)

| Printed heading | Value | Unit |
| --- | --- | --- |
| `freq` | Reporting event (`day`, `mon`, or `year`) | — |
| `soil_lyr` | Soil layer number (`-1` for profile) | — |
| `soil_depth` | Integer depth to layer bottom (`-1` for profile) | mm |
| `jday` | Day of year | — |
| `mon` | Month | — |
| `day` | Day of month | — |
| `yr` | Calendar year | — |
| `unit` | HRU number | — |
| `gis_id` | HRU GIS identifier | — |
| `name` | HRU name | — |
| `residue_c` | Plant residue carbon | kg/ha |
| `structural_c` | Structural litter carbon | kg/ha |
| `metabolic_c` | Metabolic litter carbon | kg/ha |
| `hs_c` | Slow humus carbon | kg/ha |
| `hp_c` | Passive humus carbon | kg/ha |
| `microbrial_c` | Microbial biomass carbon | kg/ha |
| `lignin_c` | Lignin in structural litter carbon | kg/ha |
| `nonlignin_c` | Non-lignin structural litter carbon | kg/ha |
| `water_c` | Water-soluble pool carbon | kg/ha |
| `manure_c` | Manure pool carbon | kg/ha |
| `root_mass` | Live root biomass mass | kg/ha |
| `soil_water` | Layer water fraction or profile calculation described above | mm/mm printed |

[Back to the hru_cb reports](output-files-generated-by-hru_cb.md).
