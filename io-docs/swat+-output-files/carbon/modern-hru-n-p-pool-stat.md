# Modern HRU nitrogen and phosphorus pools by layer

Enable the desired periods on the named `hru_cb_npool` row in [print.prt](../../introduction-1/simulation-settings/print.prt/README.md). Files are named `hru_n_p_pool_stat_day`, `hru_n_p_pool_stat_mon`, `hru_n_p_pool_stat_yr`, or `hru_n_p_pool_stat_aa` with a `.txt` extension. Set `csvout` to `y` for CSV copies. The writer runs at each selected reporting event after the skipped years. Monthly and yearly rows are snapshots on the period's final simulated day. The `_aa` file is an end-of-simulation snapshot. [Output calls](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L506)

The first seven headings are `jday`, `mon`, `day`, `yr`, `unit`, `gis_id`, and `name`. Each layer block then has `N` columns, where `N` is the number of output layers. By default it is the largest soil layer count across the full HRUs. Set a different count in [carbon_layers.prt](../../introduction-1/simulation-settings/carbon_layers.prt/README.md). The writer fills missing layer positions with `-99` and leaves out layers beyond `N`. [Default layer count](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_init.f90#L24), [Missing layers](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_module.f90#L665)

## Column order

The output controller calls the writer once per full HRU, and the writer loops over every full HRU on each call. With multiple full HRUs, the file repeats the full set of rows at each reporting event. [Output controller](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L470), [Writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_write.f90#L92)

Each row has `7 + 19 × N` columns. After the identifiers, the depth block comes first, then all nine nitrogen blocks, then all nine phosphorus blocks. The writer emits all layers of a block before starting the next block. The file prints the column labels without a separate units row. [Header generator](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_module.f90#L577), [Pool block names](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_module.f90#L33), [Row writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_write.f90#L361)

| Block | Value | Unit |
| --- | --- | --- |
| `depth_lyr1` … `depth_lyrN` | Depth to the bottom of each layer | mm |
| `tot_pool_n_lyr1` … `tot_pool_n_lyrN` | Total nitrogen | kg/ha |
| `residue_n_lyr1` … `residue_n_lyrN` | Plant residue nitrogen | kg/ha |
| `structural_n_lyr1` … `structural_n_lyrN` | Structural litter nitrogen | kg/ha |
| `metabolic_n_lyr1` … `metabolic_n_lyrN` | Metabolic litter nitrogen | kg/ha |
| `hs_n_lyr1` … `hs_n_lyrN` | Slow humus nitrogen | kg/ha |
| `hp_n_lyr1` … `hp_n_lyrN` | Passive humus nitrogen | kg/ha |
| `microbial_n_lyr1` … `microbial_n_lyrN` | Microbial biomass nitrogen | kg/ha |
| `lignin_n_lyr1` … `lignin_n_lyrN` | Lignin in structural litter nitrogen | kg/ha |
| `nonlignin_n_lyr1` … `nonlignin_n_lyrN` | Non-lignin structural litter nitrogen | kg/ha |
| `tot_pool_p_lyr1` … `tot_pool_p_lyrN` | Total phosphorus | kg/ha |
| `residue_p_lyr1` … `residue_p_lyrN` | Plant residue phosphorus | kg/ha |
| `structural_p_lyr1` … `structural_p_lyrN` | Structural litter phosphorus | kg/ha |
| `metabolic_p_lyr1` … `metabolic_p_lyrN` | Metabolic litter phosphorus | kg/ha |
| `hs_p_lyr1` … `hs_p_lyrN` | Slow humus phosphorus | kg/ha |
| `hp_p_lyr1` … `hp_p_lyrN` | Passive humus phosphorus | kg/ha |
| `microbial_p_lyr1` … `microbial_p_lyrN` | Microbial biomass phosphorus | kg/ha |
| `lignin_p_lyr1` … `lignin_p_lyrN` | Lignin in structural litter phosphorus | kg/ha |
| `nonlignin_p_lyr1` … `nonlignin_p_lyrN` | Non-lignin structural litter phosphorus | kg/ha |

Each layer total includes residue, structural and metabolic litter, slow and passive humus, microbial biomass, water-soluble material, and manure. The water and manure pools contribute to the total without separate columns. Lignin and non-lignin are parts of structural litter and are counted through that pool in the total. [Nitrogen calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_write.f90#L382), [Phosphorus calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_write.f90#L401)

The unsuffixed legacy report has layer and profile rows. [Legacy nitrogen and phosphorus pool table](hru-n-p-pool-stat.md)
