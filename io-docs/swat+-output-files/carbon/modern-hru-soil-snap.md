# Modern HRU soil snapshots by layer

Use the named `hru_cb_snap` row in [print.prt](../../introduction-1/simulation-settings/print.prt/README.md). Set the desired columns to `y`. Set `csvout` to `y` for CSV copies. [Print row](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_print_codes_read.f90#L497), [File openers](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_init.f90#L378)

| Print column | File stem | What it records |
| --- | --- | --- |
| Daily | `hru_soil_snap_day` | Soil properties on the reporting day |
| Monthly | `hru_soil_snap_mon` | Soil properties on the last simulated day of the month |
| Yearly | `hru_soil_snap_yr` | Soil properties on the last simulated day of the year |
| Average annual | `hru_soil_snap_tot` | Beginning and ending snapshots, with the beginning write gated by `carbon = 2` |

The fourth switch opens `_tot`. It does not create an `_aa` file. With `carbon = 2` in [codes.bsn](../../introduction-1/basin-1/codes.bsn/README.md), the opener writes the beginning rows after soil carbon initialization. At the end of a simulation that reaches the reporting code, the first full HRU triggers a single write of all ending rows. The ending path checks the fourth switch for all carbon modes. The shared row layout has no stage column. When both stages are written, the beginning set comes first. [Initialization](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/main.f90.in#L125), [Beginning write](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_init.f90#L382), [Ending write](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hru_output.f90#L304), [Snapshot writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_write.f90#L80)

{% hint style="warning" %}
For the daily, monthly, and yearly files, the output controller calls the writer once per full HRU, and the writer loops over every full HRU on each call. With multiple full HRUs, the full set of rows repeats at each reporting event. [Output controller](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L470), [Period writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_write.f90#L92)
{% endhint %}

## Column order

All four file pairs share the same layout. Each row has `7 + 14 × N` columns. The seven identifiers are `jday`, `mon`, `day`, `yr`, `unit`, `gis_id`, and `name`. Each block below contains `N` output layers. The default is the largest soil layer count across full HRUs. [carbon_layers.prt](../../introduction-1/simulation-settings/carbon_layers.prt/README.md) can override it. The writer uses `-99` for missing layer positions and omits layers beyond `N`. The files print column headings without a units row. [Header generator](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_module.f90#L577), [Block names](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_module.f90#L58), [Data writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_write.f90#L663)

| Block | Value | Unit |
| --- | --- | --- |
| `depth_lyr1` … `depth_lyrN` | Depth to the bottom of the layer | mm |
| `bd_lyr1` … `bd_lyrN` | Bulk density | Mg/m3 |
| `awc_lyr1` … `awc_lyrN` | Available water capacity | mm/mm |
| `soil_k_lyr1` … `soil_k_lyrN` | Saturated hydraulic conductivity | mm/h |
| `tot_c_lyr1` … `tot_c_lyrN` | Total soil carbon mass in the layer | kg C/ha |
| `clay_lyr1` … `clay_lyrN` | Clay content | % |
| `silt_lyr1` … `silt_lyrN` | Silt content | % |
| `sand_lyr1` … `sand_lyrN` | Sand content | % |
| `rock_lyr1` … `rock_lyrN` | Rock fragment content | % |
| `alb_lyr1` … `alb_lyrN` | Moist soil albedo | fraction |
| `usle_k_lyr1` … `usle_k_lyrN` | USLE soil erodibility factor | — |
| `ec_lyr1` … `ec_lyrN` | Electrical conductivity | dS/m |
| `caco3_lyr1` … `caco3_lyrN` | Calcium carbonate content | % |
| `ph_lyr1` … `ph_lyrN` | Soil pH | — |

The writer uses `soil1%tot%c` in kg C/ha at every stage. For the older beginning and ending files, see [Legacy soil snapshots](../soil/README.md).
