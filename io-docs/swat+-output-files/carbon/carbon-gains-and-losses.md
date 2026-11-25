# Carbon Gains and Losses

The `hru_carb_gl_*` and `lsu_carb_gl_*` files use the `hru_cb_gl` and `lsu_cb_gl` rows in [print.prt](../../introduction-1/simulation-settings/print.prt/README.md). See [Modern Carbon and Nitrogen Outputs](modern-carbon-nitrogen.md#how-to-produce-these-files) for the period columns and CSV setting.

Each row has 28 columns in the order shown. The first seven identify the reporting date and object. The units line reports `kg C/ha` for every process column.

| Field | Unit |
| --- | --- |
| `jday` | |
| `mon` | |
| `day` | |
| `yr` | |
| `unit` | |
| `gis_id` | |
| `name` | |
| `sed_c` | kg C/ha |
| `surq_c` | kg C/ha |
| `latq_c` | kg C/ha |
| `perc_c` | kg C/ha |
| `res_decay` | kg C/ha |
| `man_app_c` | kg C/ha |
| `man_graze_c` | kg C/ha |
| `rsp_c` | kg C/ha |
| `soil_emit_c` | kg C/ha |
| `plant_surf_c` | kg C/ha |
| `plant_root_c` | kg C/ha |
| `rsd_surfdecay_c` | kg C/ha |
| `rsd_rootdecay_c` | kg C/ha |
| `harv_stov_c` | kg C/ha |
| `rsd_emit_c` | kg C/ha |
| `npp_c` | kg C/ha |
| `harv_abgr_c` | kg C/ha |
| `harv_root_c` | kg C/ha |
| `drop_c` | kg C/ha |
| `grazeat_c` | kg C/ha |
| `plant_emit_c` | kg C/ha |

[HRU writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_carbon_output.f90#L31), [LSU writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lsu_carbon_output.f90#L24)
