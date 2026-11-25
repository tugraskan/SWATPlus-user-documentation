# Modern HRU decomposition drivers by layer

Set `carbon = 2` in [codes.bsn](../../introduction-1/basin-1/codes.bsn/README.md). Set the desired columns of the named `hru_cb_drv` row in [print.prt](../../introduction-1/simulation-settings/print.prt/README.md) to `y`. The files use the `hru_carb_drv` stem with `_day`, `_mon`, `_yr`, or `_aa` and a `.txt` extension. Set `csvout` to `y` for CSV copies. Each row reports the selected day's values. Monthly and yearly files use the last simulated day of the period. The `_aa` file is an end-of-simulation snapshot. [Openers](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_init.f90#L408), [Reporting calls](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L521)

{% hint style="warning" %}
In this source revision, the output controller calls the writer once per full HRU, and the writer itself loops over every full HRU. Each enabled file therefore receives one copy of the full set of HRU rows for each full HRU at a reporting event. [Output controller](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L470), [Writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_carbvar_write.f90#L42)
{% endhint %}

## Column order

Each row has `7 + 15 × N` columns. The first seven headings are `jday`, `mon`, `day`, `yr`, `unit`, `gis_id`, and `name`. Each block below contains `N` columns. By default, `N` is the largest soil layer count across full HRUs. Set another count in [carbon_layers.prt](../../introduction-1/simulation-settings/carbon_layers.prt/README.md). The writer fills missing layers with `-99` and leaves out layers beyond `N`. There is no separate units row. [Header and layer padding](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_module.f90#L577), [Default layer count](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_init.f90#L24)

| Block | Value | Unit |
| --- | --- | --- |
| `depth_lyr1` … `depth_lyrN` | Depth to the bottom of each layer | mm |
| `sut_lyr1` … `sut_lyrN` | Soil water factor | — |
| `tillagef_lyr1` … `tillagef_lyrN` | Combined tillage and biomixing factor | — |
| `cons_bmix_lyr1` … `cons_bmix_lyrN` | Biomixing coefficient stored in the layer | — |
| `tillagef_biomix_lyr1` … `tillagef_biomix_lyrN` | Biomixing component of the tillage factor | — |
| `tillagef_tillmix_lyr1` … `tillagef_tillmix_lyrN` | Tillage component of the tillage factor | — |
| `till_eff_lyr1` … `till_eff_lyrN` | Tillage effect factor | — |
| `cdg_lyr1` … `cdg_lyrN` | Soil temperature factor | — |
| `ox_lyr1` … `ox_lyrN` | Soil oxygen factor | — |
| `cs_lyr1` … `cs_lyrN` | Combined decomposition control factor | — |
| `no3_lyr1` … `no3_lyrN` | Stored nitrate diagnostic | kg/ha |
| `nh4_lyr1` … `nh4_lyrN` | Stored ammonium diagnostic | kg/ha |
| `co2_resp_lyr1` … `co2_resp_lyrN` | Respired carbon | kg C/ha |
| `soil_temp_lyr1` … `soil_temp_lyrN` | Soil temperature | °C |
| `emix_lyr1` … `emix_lyrN` | Fraction of the layer mixed by tillage or biomixing | — |

The driver fields include the nitrate and ammonium diagnostics stored by the decomposition routine, respired carbon, and the layer's mixing fraction. [Diagnostic assignments](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cbn_zhang2.f90#L996), [Driver blocks](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_carbvar_write.f90#L87)

[Back to Modern Carbon and Nitrogen Outputs](modern-carbon-nitrogen.md).
