# Soil Carbon Fluxes

The `hru_scf_*` and `lsu_scf_*` files use the `hru_cb_trf` and `lsu_cb_trf` rows in [print.prt](../../introduction-1/simulation-settings/print.prt/README.md). See [Modern Carbon and Nitrogen Outputs](modern-carbon-nitrogen.md#how-to-produce-these-files) for the period columns and CSV setting.

Each row has 20 columns in the order shown. The first seven identify the reporting date and object. The units line reports `kg C/ha` for every process column.

| Field | Unit |
| --- | --- |
| `jday` | |
| `mon` | |
| `day` | |
| `yr` | |
| `unit` | |
| `gis_id` | |
| `name` | |
| `meta_micr` | kg C/ha |
| `str_micr` | kg C/ha |
| `str_hs` | kg C/ha |
| `co2_meta` | kg C/ha |
| `co2_str` | kg C/ha |
| `micr_hs` | kg C/ha |
| `micr_hp` | kg C/ha |
| `hs_micr` | kg C/ha |
| `hs_hp` | kg C/ha |
| `hp_micr` | kg C/ha |
| `co2_micr` | kg C/ha |
| `co2_hs` | kg C/ha |
| `co2_hp` | kg C/ha |

[HRU writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_carbon_output.f90#L37), [LSU writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lsu_carbon_output.f90#L24)
