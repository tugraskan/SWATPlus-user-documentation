# Modern HRU carbon and nitrogen fluxes by layer

Set `carbon = 2` in [codes.bsn](../../introduction-1/basin-1/codes.bsn/README.md). Set the desired daily, monthly, yearly, or average-annual columns to `y` on the named `hru_cb_flux` row in [print.prt](../../introduction-1/simulation-settings/print.prt/README.md). Files use the stem `hru_cflux_stat` and suffixes `_day`, `_mon`, `_yr`, or `_aa`. Set `csvout` to `y` for CSV copies. [File openers](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_init.f90#L391)

Each row starts with `jday`, `mon`, `day`, `yr`, `unit`, `gis_id`, and `name`. Each subsequent block has `N` columns, one per output layer. Set `N` in [carbon_layers.prt](../../introduction-1/simulation-settings/carbon_layers.prt/README.md) or use the default, the largest layer count across full HRUs. Missing layer positions are filled with `-99`, and layers beyond `N` are omitted. The files print headings without a separate units row. [Layer count](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_init.f90#L24), [Headers and padding](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_module.f90#L577)

The daily, monthly, and yearly files show fluxes from the reporting day. In `_aa`, the writer divides the cumulative flux in each layer by `max(time%yrs_prt, 1.0)`. The decomposition routine accumulates flux during the simulation without checking skipped print years, so the numerator can include flux from those years. The units below apply to a reporting day's mass per hectare. The `_aa` columns are mass per hectare per year as calculated by that divisor. [Flux writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_write.f90#L492), [Flux accumulation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cbn_zhang2.f90#L1010), [Year count](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_control.f90#L145)

## Column order

The output controller calls the writer once per full HRU, and the writer loops over every full HRU on each call. With multiple full HRUs, the file repeats the full set of rows at each reporting event. [Output controller](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L470), [Writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_write.f90#L92)

Each row has `7 + 38 × N` columns. After the identifiers, the writer emits all layers of each block below before starting the next block.

| Block | Value | Unit |
| --- | --- | --- |
| `depth_lyr1` … `depth_lyrN` | Depth to the bottom of each layer | mm |
| `cfmets1_lyr1` … `cfmets1_lyrN` | Carbon transferred from metabolic litter to microbial biomass | kg C/ha |
| `cfstrs1_lyr1` … `cfstrs1_lyrN` | Carbon transferred from non-lignin structural litter to microbial biomass | kg C/ha |
| `cfstrs2_lyr1` … `cfstrs2_lyrN` | Carbon transferred from lignin in structural litter to slow humus | kg C/ha |
| `efmets1_lyr1` … `efmets1_lyrN` | Nitrogen transferred from metabolic litter to microbial biomass | kg N/ha |
| `efstrs1_lyr1` … `efstrs1_lyrN` | Nitrogen transferred from non-lignin structural litter to microbial biomass | kg N/ha |
| `efstrs2_lyr1` … `efstrs2_lyrN` | Nitrogen transferred from lignin in structural litter to slow humus | kg N/ha |
| `immmets1_lyr1` … `immmets1_lyrN` | Nitrogen immobilized during transfer from metabolic litter to microbial biomass | kg N/ha |
| `immstrs1_lyr1` … `immstrs1_lyrN` | Nitrogen immobilized during transfer from non-lignin structural litter to microbial biomass | kg N/ha |
| `immstrs2_lyr1` … `immstrs2_lyrN` | Nitrogen immobilized during transfer from lignin in structural litter to slow humus | kg N/ha |
| `mnrmets1_lyr1` … `mnrmets1_lyrN` | Nitrogen mineralized during transfer from metabolic litter to microbial biomass | kg N/ha |
| `mnrstrs1_lyr1` … `mnrstrs1_lyrN` | Nitrogen mineralized during transfer from non-lignin structural litter to microbial biomass | kg N/ha |
| `mnrstrs2_lyr1` … `mnrstrs2_lyrN` | Nitrogen mineralized during transfer from lignin in structural litter to slow humus | kg N/ha |
| `co2fmet_lyr1` … `co2fmet_lyrN` | Carbon respired as CO₂ during metabolic litter decomposition | kg C/ha |
| `co2fstr_lyr1` … `co2fstr_lyrN` | Carbon respired as CO₂ during structural litter decomposition | kg C/ha |
| `cfs1s2_lyr1` … `cfs1s2_lyrN` | Carbon transferred from microbial biomass to slow humus | kg C/ha |
| `cfs1s3_lyr1` … `cfs1s3_lyrN` | Carbon transferred from microbial biomass to passive humus | kg C/ha |
| `cfs2s1_lyr1` … `cfs2s1_lyrN` | Carbon transferred from slow humus to microbial biomass | kg C/ha |
| `cfs2s3_lyr1` … `cfs2s3_lyrN` | Carbon transferred from slow humus to passive humus | kg C/ha |
| `cfs3s1_lyr1` … `cfs3s1_lyrN` | Carbon transferred from passive humus to microbial biomass | kg C/ha |
| `efs1s2_lyr1` … `efs1s2_lyrN` | Nitrogen transferred from microbial biomass to slow humus | kg N/ha |
| `efs1s3_lyr1` … `efs1s3_lyrN` | Nitrogen transferred from microbial biomass to passive humus | kg N/ha |
| `efs2s1_lyr1` … `efs2s1_lyrN` | Nitrogen transferred from slow humus to microbial biomass | kg N/ha |
| `efs2s3_lyr1` … `efs2s3_lyrN` | Nitrogen transferred from slow humus to passive humus | kg N/ha |
| `efs3s1_lyr1` … `efs3s1_lyrN` | Nitrogen transferred from passive humus to microbial biomass | kg N/ha |
| `imms1s2_lyr1` … `imms1s2_lyrN` | Nitrogen immobilized during transfer from microbial biomass to slow humus | kg N/ha |
| `imms1s3_lyr1` … `imms1s3_lyrN` | Nitrogen immobilized during transfer from microbial biomass to passive humus | kg N/ha |
| `imms2s1_lyr1` … `imms2s1_lyrN` | Nitrogen immobilized during transfer from slow humus to microbial biomass | kg N/ha |
| `imms2s3_lyr1` … `imms2s3_lyrN` | Nitrogen immobilized during transfer from slow humus to passive humus | kg N/ha |
| `imms3s1_lyr1` … `imms3s1_lyrN` | Nitrogen immobilized during transfer from passive humus to microbial biomass | kg N/ha |
| `mnrs1s2_lyr1` … `mnrs1s2_lyrN` | Nitrogen mineralized during transfer from microbial biomass to slow humus | kg N/ha |
| `mnrs1s3_lyr1` … `mnrs1s3_lyrN` | Nitrogen mineralized during transfer from microbial biomass to passive humus | kg N/ha |
| `mnrs2s1_lyr1` … `mnrs2s1_lyrN` | Nitrogen mineralized during transfer from slow humus to microbial biomass | kg N/ha |
| `mnrs2s3_lyr1` … `mnrs2s3_lyrN` | Nitrogen mineralized during transfer from slow humus to passive humus | kg N/ha |
| `mnrs3s1_lyr1` … `mnrs3s1_lyrN` | Nitrogen mineralized during transfer from passive humus to microbial biomass | kg N/ha |
| `co2fs1_lyr1` … `co2fs1_lyrN` | Carbon respired as CO₂ during microbial biomass decomposition | kg C/ha |
| `co2fs2_lyr1` … `co2fs2_lyrN` | Carbon respired as CO₂ during slow humus decomposition | kg C/ha |
| `co2fs3_lyr1` … `co2fs3_lyrN` | Carbon respired as CO₂ during passive humus decomposition | kg C/ha |

See the [legacy table](hru-cflux-stat.md) for the unsuffixed TXT and CSV layout.
