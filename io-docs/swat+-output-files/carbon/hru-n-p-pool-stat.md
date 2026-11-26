# Legacy HRU soil nitrogen and phosphorus pools

Files `hru_n_p_pool_stat.txt` and `hru_n_p_pool_stat.csv` use the named `hru_cb` row in [print.prt](../../introduction-1/simulation-settings/print.prt/README.md). Set `y` for profile rows or lowercase `l` for profile and layer rows. Set `csvout` to `y` for the CSV copy. Daily, monthly, and yearly events share the file. Rows show values on the reporting date. [File opener](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_legacy_module.f90#L472), [Reporting calls](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L539-L548), [Data writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_write_historical.f90#L298)

The 32 columns contain a nitrogen block followed by a phosphorus block. Each total adds residue, structural litter, metabolic litter, slow humus, passive humus, microbial biomass, water-soluble material, and manure. The lignin and non-lignin columns describe parts of structural litter. The totals use the structural litter pool once. [Layer and profile totals](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_write_historical.f90#L299)

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
| `tot_pool_n` | Total organic pool nitrogen | kg/ha |
| `residue_n` | Plant residue nitrogen | kg/ha |
| `structural_n` | Structural litter nitrogen | kg/ha |
| `metabolic_n` | Metabolic litter nitrogen | kg/ha |
| `hs_n` | Slow humus nitrogen | kg/ha |
| `hp_n` | Passive humus nitrogen | kg/ha |
| `microbial_n` | Microbial biomass nitrogen | kg/ha |
| `lignin_n` | Lignin in structural litter nitrogen | kg/ha |
| `nonlignin_n` | Non-lignin structural litter nitrogen | kg/ha |
| `water_n` | Water-soluble pool nitrogen | kg/ha |
| `manure_n` | Manure pool nitrogen | kg/ha |
| `tot_pool_p` | Total organic pool phosphorus | kg/ha |
| `residue_p` | Plant residue phosphorus | kg/ha |
| `structural_p` | Structural litter phosphorus | kg/ha |
| `metabolic_p` | Metabolic litter phosphorus | kg/ha |
| `hs_p` | Slow humus phosphorus | kg/ha |
| `hp_p` | Passive humus phosphorus | kg/ha |
| `microbial_p` | Microbial biomass phosphorus | kg/ha |
| `lignin_p` | Lignin in structural litter phosphorus | kg/ha |
| `nonlignin_p` | Non-lignin structural litter phosphorus | kg/ha |
| `water_p` | Water-soluble pool phosphorus | kg/ha |
| `manure_p` | Manure pool phosphorus | kg/ha |

[Back to the hru_cb reports](output-files-generated-by-hru_cb.md).
