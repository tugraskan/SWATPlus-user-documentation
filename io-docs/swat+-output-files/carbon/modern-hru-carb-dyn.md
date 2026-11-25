# Modern HRU organic pool dynamics by layer

Set `carbon = 2` in [codes.bsn](../../introduction-1/basin-1/codes.bsn/README.md). Set the desired columns of the named `hru_cb_dyn` row in [print.prt](../../introduction-1/simulation-settings/print.prt/README.md) to `y`. The files use the `hru_carb_dyn` stem with `_day`, `_mon`, `_yr`, or `_aa` and a `.txt` extension. Set `csvout` to `y` for CSV copies. Each row reports the selected day's values. Monthly and yearly files use the last simulated day of the period. The `_aa` file is an end-of-simulation snapshot. [Openers](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_init.f90#L408), [Reporting calls](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L521)

{% hint style="warning" %}
In this source revision, the output controller calls the writer once per full HRU, and the writer itself loops over every full HRU. Each enabled file therefore receives one copy of the full set of HRU rows for each full HRU at a reporting event. [Output controller](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L470), [Writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_carbvar_write.f90#L42)
{% endhint %}

## Column order

Each row has `7 + 22 × N` columns. The first seven headings are `jday`, `mon`, `day`, `yr`, `unit`, `gis_id`, and `name`. Each block below contains `N` columns. By default, `N` is the largest soil layer count across full HRUs. Set another count in [carbon_layers.prt](../../introduction-1/simulation-settings/carbon_layers.prt/README.md). The writer fills missing layers with `-99` and leaves out layers beyond `N`. There is no separate units row. [Header and layer padding](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_module.f90#L577), [Default layer count](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_init.f90#L24)

| Block | Value | Unit |
| --- | --- | --- |
| `depth_lyr1` … `depth_lyrN` | Depth to the bottom of each layer | mm |
| `asp_lyr1` … `asp_lyrN` | Fraction of decomposed slow humus carbon allocated to passive humus | — |
| `abp_lyr1` … `abp_lyrN` | Fraction of decomposed microbial biomass carbon allocated to passive humus | — |
| `abco2_lyr1` … `abco2_lyrN` | Respired fraction of decomposed microbial biomass carbon | — |
| `a1co2_lyr1` … `a1co2_lyrN` | Respired fraction of decomposed metabolic and non-lignin structural litter carbon | — |
| `asco2_lyr1` … `asco2_lyrN` | Respired fraction of decomposed slow humus carbon | — |
| `apco2_lyr1` … `apco2_lyrN` | Respired fraction of decomposed passive humus carbon | — |
| `ncbm_lyr1` … `ncbm_lyrN` | Microbial biomass nitrogen-to-carbon ratio | kg N/kg C |
| `nchp_lyr1` … `nchp_lyrN` | Passive humus nitrogen-to-carbon ratio | kg N/kg C |
| `nchs_lyr1` … `nchs_lyrN` | Slow humus nitrogen-to-carbon ratio | kg N/kg C |
| `bmctp_lyr1` … `bmctp_lyrN` | Potential transformation of microbial biomass carbon | kg/ha/day |
| `bmntp_lyr1` … `bmntp_lyrN` | Potential transformation of microbial biomass nitrogen | kg/ha/day |
| `hsctp_lyr1` … `hsctp_lyrN` | Potential transformation of slow humus carbon | kg/ha/day |
| `hsntp_lyr1` … `hsntp_lyrN` | Potential transformation of slow humus nitrogen | kg/ha/day |
| `hpctp_lyr1` … `hpctp_lyrN` | Potential transformation of passive humus carbon | kg/ha/day |
| `hpntp_lyr1` … `hpntp_lyrN` | Potential transformation of passive humus nitrogen | kg/ha/day |
| `lmctp_lyr1` … `lmctp_lyrN` | Potential transformation of metabolic litter carbon | kg/ha/day |
| `lmntp_lyr1` … `lmntp_lyrN` | Potential transformation of metabolic litter nitrogen | kg/ha/day |
| `lsctp_lyr1` … `lsctp_lyrN` | Potential transformation of structural litter carbon | kg/ha/day |
| `lslctp_lyr1` … `lslctp_lyrN` | Potential transformation of lignin carbon in structural litter | kg/ha/day |
| `lslnctp_lyr1` … `lslnctp_lyrN` | Potential transformation of non-lignin carbon in structural litter | kg/ha/day |
| `lsntp_lyr1` … `lsntp_lyrN` | Potential transformation of structural litter nitrogen | kg/ha/day |

The six allocation blocks match their printed headings. The modern writer selects each member explicitly. The legacy allocation file has a different positional mapping. [Modern dynamics writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_carbvar_write.f90#L124), [Legacy allocation table](hru-org-allo-vars.md)

[Back to Modern Carbon and Nitrogen Outputs](modern-carbon-nitrogen.md).
