# Legacy HRU soil carbon and nitrogen fluxes

Files `hru_cflux_stat.txt` and `hru_cflux_stat.csv` use the named `hru_cb` row in [print.prt](../../introduction-1/simulation-settings/print.prt/README.md). Set `carbon = 2` in [codes.bsn](../../introduction-1/basin-1/codes.bsn/README.md) and, on SWAT+ dev, [cbn\_diag\_int](../../introduction-1/carbon/carbon.bsn/cbn_diag_int.md) `= 1` in carbon.bsn to enable the diagnostics; the `hru_cb` letter no longer does. Enabled periods use `y` for profile rows and `l` for profile and layer rows. Set `csvout` to `y` for the CSV copy. Daily, monthly, and yearly events share the file. Rows show values on the reporting date. [File opener](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_legacy_module.f90#L472), [Reporting calls](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L539-L548), [Data writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_write_historical.f90#L350)

The 47 headings match the 47 data values in order. The units record has 45 entries because it omits units for `mnrs3s1` and `co2fs1`. The last two printed units belong to `co2fs2` and `co2fs3`. The table below gives the unit for each actual value. Fluxes represent the reporting day's transfers, immobilization, mineralization, and respiration. The profile value sums the layer fluxes. [Units declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_legacy_module.f90#L111), [Flux declarations](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_module.f90#L168), [Daily accumulation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cbn_zhang2.f90#L1010)

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
| `cfmets1` | Carbon transferred from metabolic litter to microbial biomass | kg C/ha |
| `cfstrs1` | Carbon transferred from non-lignin structural litter to microbial biomass | kg C/ha |
| `cfstrs2` | Carbon transferred from lignin in structural litter to slow humus | kg C/ha |
| `efmets1` | Nitrogen transferred from metabolic litter to microbial biomass | kg N/ha |
| `efstrs1` | Nitrogen transferred from non-lignin structural litter to microbial biomass | kg N/ha |
| `efstrs2` | Nitrogen transferred from lignin in structural litter to slow humus | kg N/ha |
| `immmets1` | Nitrogen immobilized during transfer from metabolic litter to microbial biomass | kg N/ha |
| `immstrs1` | Nitrogen immobilized during transfer from non-lignin structural litter to microbial biomass | kg N/ha |
| `immstrs2` | Nitrogen immobilized during transfer from lignin in structural litter to slow humus | kg N/ha |
| `mnrmets1` | Nitrogen mineralized during transfer from metabolic litter to microbial biomass | kg N/ha |
| `mnrstrs1` | Nitrogen mineralized during transfer from non-lignin structural litter to microbial biomass | kg N/ha |
| `mnrstrs2` | Nitrogen mineralized during transfer from lignin in structural litter to slow humus | kg N/ha |
| `co2fmet` | Carbon respired as CO₂ during metabolic litter decomposition | kg C/ha |
| `co2fstr` | Carbon respired as CO₂ during structural litter decomposition | kg C/ha |
| `cfs1s2` | Carbon transferred from microbial biomass to slow humus | kg C/ha |
| `cfs1s3` | Carbon transferred from microbial biomass to passive humus | kg C/ha |
| `cfs2s1` | Carbon transferred from slow humus to microbial biomass | kg C/ha |
| `cfs2s3` | Carbon transferred from slow humus to passive humus | kg C/ha |
| `cfs3s1` | Carbon transferred from passive humus to microbial biomass | kg C/ha |
| `efs1s2` | Nitrogen transferred from microbial biomass to slow humus | kg N/ha |
| `efs1s3` | Nitrogen transferred from microbial biomass to passive humus | kg N/ha |
| `efs2s1` | Nitrogen transferred from slow humus to microbial biomass | kg N/ha |
| `efs2s3` | Nitrogen transferred from slow humus to passive humus | kg N/ha |
| `efs3s1` | Nitrogen transferred from passive humus to microbial biomass | kg N/ha |
| `imms1s2` | Nitrogen immobilized during transfer from microbial biomass to slow humus | kg N/ha |
| `imms1s3` | Nitrogen immobilized during transfer from microbial biomass to passive humus | kg N/ha |
| `imms2s1` | Nitrogen immobilized during transfer from slow humus to microbial biomass | kg N/ha |
| `imms2s3` | Nitrogen immobilized during transfer from slow humus to passive humus | kg N/ha |
| `imms3s1` | Nitrogen immobilized during transfer from passive humus to microbial biomass | kg N/ha |
| `mnrs1s2` | Nitrogen mineralized during transfer from microbial biomass to slow humus | kg N/ha |
| `mnrs1s3` | Nitrogen mineralized during transfer from microbial biomass to passive humus | kg N/ha |
| `mnrs2s1` | Nitrogen mineralized during transfer from slow humus to microbial biomass | kg N/ha |
| `mnrs2s3` | Nitrogen mineralized during transfer from slow humus to passive humus | kg N/ha |
| `mnrs3s1` | Nitrogen mineralized during transfer from passive humus to microbial biomass | kg N/ha |
| `co2fs1` | Carbon respired as CO₂ during microbial biomass decomposition | kg C/ha |
| `co2fs2` | Carbon respired as CO₂ during slow humus decomposition | kg C/ha |
| `co2fs3` | Carbon respired as CO₂ during passive humus decomposition | kg C/ha |

[Back to the hru_cb reports](output-files-generated-by-hru_cb.md).
