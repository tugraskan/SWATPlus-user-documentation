# Modern HRU soil carbon stocks by layer

Enable the desired periods on the named `hru_cb_lyr` row in [print.prt](../../introduction-1/simulation-settings/print.prt/README.md). Files are named `hru_cbn_lyr_day`, `hru_cbn_lyr_mon`, `hru_cbn_lyr_yr`, or `hru_cbn_lyr_aa` with a `.txt` extension. Set `csvout` to `y` for CSV copies. The writer runs at each selected reporting event after the skipped years. Monthly and yearly rows are snapshots on the period's final simulated day. The `_aa` file is an end-of-simulation snapshot. [Output calls](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L506)

The first seven headings are `jday`, `mon`, `day`, `yr`, `unit`, `gis_id`, and `name`. Each layer block then has `N` columns, where `N` is the number of output layers. By default it is the largest soil layer count across the full HRUs. Set a different count in [carbon_layers.prt](../../introduction-1/simulation-settings/carbon_layers.prt/README.md). The writer fills missing layer positions with `-99` and leaves out layers beyond `N`. [Default layer count](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_init.f90#L24), [Missing layers](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_module.f90#L665)

## Column order

The output controller calls the writer once per full HRU, and the writer loops over every full HRU on each call. With multiple full HRUs, the file repeats the full set of rows at each reporting event. [Output controller](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L470), [Writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_write.f90#L92)

Each row has `9 + 3 × N` columns. After the identifiers, the order is shown below. The 300 mm totals use the full soil profile, including any layers beyond the output layer count that contribute above 300 mm. A layer crossing 300 mm contributes the fraction of its thickness within that depth. The writer converts carbon from kg/ha to Mg/ha. [Header generator](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_module.f90#L617), [Stock calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_write.f90#L181), [Row writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_write.f90#L609)

| Heading or block | Value | Unit |
| --- | --- | --- |
| `depth_lyr1` … `depth_lyrN` | Depth to the bottom of each layer | mm |
| `tot_300_sum` | Total soil carbon in the top 300 mm | Mg/ha |
| `tot_lyr1` … `tot_lyrN` | Total soil carbon in each whole layer | Mg/ha |
| `seq_300_sum` | Sequestered soil carbon in the top 300 mm | Mg/ha |
| `seq_lyr1` … `seq_lyrN` | Sequestered soil carbon in each whole layer | Mg/ha |

With `carbon = 2`, total carbon includes structural litter, metabolic litter, passive humus, slow humus, and microbial biomass. Sequestered carbon uses passive humus, slow humus, and microbial biomass. With `carbon = 0`, both groups use active humus, stable humus, and microbial biomass. [Carbon pool assignments](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cbn_zhang2.f90#L1021), [Stock writer calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_write.f90#L196)

The unsuffixed legacy reports have their own tables. [Legacy total soil carbon](hru-cbn-lyr.md), [Legacy sequestered soil carbon](hru-seq-lyr.md)
