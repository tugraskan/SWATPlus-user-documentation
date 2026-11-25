# Modern HRU carbon pools by layer

Set `carbon = 2` in [codes.bsn](../../introduction-1/basin-1/codes.bsn/README.md). Set the desired daily, monthly, yearly, or average-annual columns to `y` on the named `hru_cb_cpool` row in [print.prt](../../introduction-1/simulation-settings/print.prt/README.md). Files use the stem `hru_cpool_stat` and suffixes `_day`, `_mon`, `_yr`, or `_aa`. Set `csvout` to `y` for CSV copies. [File openers](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_init.f90#L391)

Each row starts with `jday`, `mon`, `day`, `yr`, `unit`, `gis_id`, and `name`. Each subsequent block has `N` columns, one per output layer. Set `N` in [carbon_layers.prt](../../introduction-1/simulation-settings/carbon_layers.prt/README.md) or use the default, the largest layer count across full HRUs. Missing layer positions are filled with `-99`, and layers beyond `N` are omitted. The files print headings without a separate units row. [Layer count](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_init.f90#L24), [Headers and padding](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_module.f90#L577)

The daily, monthly, and yearly files show the pool values on the reporting date. The `_aa` file is an end-of-simulation snapshot. The `soil_water` block uses the layer water fraction directly. The modern file reports layer values only. [Output calls](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L506), [Pool writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_write.f90#L276), [Soil water calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L499)

## Column order

The output controller calls the writer once per full HRU, and the writer loops over every full HRU on each call. With multiple full HRUs, the file repeats the full set of rows at each reporting event. [Output controller](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L470), [Writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_write.f90#L92)

Each row has `7 + 11 × N` columns. After the identifiers, the writer emits all layers of each block below before starting the next block.

| Block | Value | Unit |
| --- | --- | --- |
| `depth_lyr1` … `depth_lyrN` | Depth to the bottom of each layer | mm |
| `residue_c_lyr1` … `residue_c_lyrN` | Plant residue carbon | kg/ha |
| `structural_c_lyr1` … `structural_c_lyrN` | Structural litter carbon | kg/ha |
| `metabolic_c_lyr1` … `metabolic_c_lyrN` | Metabolic litter carbon | kg/ha |
| `hs_c_lyr1` … `hs_c_lyrN` | Slow humus carbon | kg/ha |
| `hp_c_lyr1` … `hp_c_lyrN` | Passive humus carbon | kg/ha |
| `microbial_c_lyr1` … `microbial_c_lyrN` | Microbial biomass carbon | kg/ha |
| `lignin_c_lyr1` … `lignin_c_lyrN` | Lignin carbon in structural litter | kg/ha |
| `nonlignin_c_lyr1` … `nonlignin_c_lyrN` | Non-lignin carbon in structural litter | kg/ha |
| `root_mass_lyr1` … `root_mass_lyrN` | Live root biomass mass | kg/ha |
| `soil_water_lyr1` … `soil_water_lyrN` | Layer water fraction including water at wilting point | mm/mm |

See the [legacy table](hru-cpool-stat.md) for the unsuffixed TXT and CSV layout.
