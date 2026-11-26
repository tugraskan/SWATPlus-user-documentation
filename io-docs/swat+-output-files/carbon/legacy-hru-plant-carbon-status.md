# Legacy HRU Plant Carbon Status

Set `carbon` to `2` in [codes.bsn](../../introduction-1/basin-1/codes.bsn/README.md). On SWAT+ dev, set [cbn\_diag\_int](../../introduction-1/carbon/carbon.bsn/cbn_diag_int.md) to `1` in carbon.bsn, and in [print.prt](../../introduction-1/simulation-settings/print.prt/README.md) use named rows with a non-`n` daily, monthly, or yearly column of `hru_cb` (`y` or `l`). For example, `hru_cb n n y n` requests yearly records. The file is `hru_plc_stat.txt`. Set `csvout` to `y` for `hru_plc_stat.csv`. (On SWAT+ main the diagnostics were switched on by a lowercase `l` in `hru_cb`.) [Diagnostic flag](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_bsn_read.f90#L93-L95), [File creation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_legacy_module.f90#L532), [Write calls](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L539-L548), [Row gate](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_write_historical.f90#L336)

The legacy diagnostic has 15 columns. The `freq` field identifies the period of each row in the shared file. The header prints `kg/ha` for the seven plant-carbon stocks. [Header definition](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_legacy_module.f90#L18), [Writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_write_historical.f90#L337)

| Field | Description | Unit |
| --- | --- | --- |
| `freq` | Reporting period marker | n/a |
| `jday` | Day of year | n/a |
| `day` | Day of month | n/a |
| `mon` | Month | n/a |
| `yr` | Calendar year | n/a |
| `unit` | HRU identifier | n/a |
| `gis_id` | GIS identifier | n/a |
| `name` | Object name | n/a |
| `total_c` | Total plant-community carbon | kg C/ha |
| `ab_gr_c` | Aboveground plant-community carbon | kg C/ha |
| `leaf_c` | Leaf carbon | kg C/ha |
| `stem_c` | Stem carbon | kg C/ha |
| `seed_c` | Seed carbon | kg C/ha |
| `root_c` | Root carbon | kg C/ha |
| `surf_rsd_c` | Surface-residue carbon | kg C/ha |

See [HRU Plant Carbon Status](hru-plant-carbon-status.md) for the current interval files.
