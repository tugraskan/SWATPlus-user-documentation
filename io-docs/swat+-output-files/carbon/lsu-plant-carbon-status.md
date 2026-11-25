# LSU Plant Carbon Status

The `lsu_plc_stat_*` files use the `lsu_cb_plt` row in [print.prt](../../introduction-1/simulation-settings/print.prt/README.md). See [Modern Carbon and Nitrogen Outputs](modern-carbon-nitrogen.md#how-to-produce-these-files) for the period columns and CSV setting.

The four interval files have eight columns in the order shown.

| Field | Description | Unit |
| --- | --- | --- |
| `jday` | Day of year | n/a |
| `mon` | Month | n/a |
| `day` | Day of month | n/a |
| `yr` | Calendar year | n/a |
| `unit` | LSU identifier | n/a |
| `gis_id` | GIS identifier | n/a |
| `name` | Object name | n/a |
| `lsu_plt_c` | Plant-community carbon weighted by contributing HRU area fractions | kg C/ha |

The LSU calculation sums `pl_mass(ihru)%tot_com%c * lsu_elem(ihru)%ru_frac` for contributing HRUs. All four reporting intervals write the current `lsu_plt_c` value, including `_aa`; it is a reporting-date stock rather than a period sum or time average ([header](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_init.f90#L1406); [calculation and writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lsu_carbon_output.f90#L40)).
