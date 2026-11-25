# HRU Nutrient Cycling

The `hru_ncycle_*` files use the `hru_nb` row in [print.prt](../../introduction-1/simulation-settings/print.prt/README.md). See [Modern Carbon and Nitrogen Outputs](modern-carbon-nitrogen.md#how-to-produce-these-files) for the period columns and CSV setting.

{% hint style="warning" %}
The inspected source opens the `hru_ncycle_*` files and prints their headers, but no data-row write to those file units is present. The fields below therefore describe printed header positions, not verified populated columns.
{% endhint %}

The 15 printed columns are listed below. The source prints `kgha` for the eight process columns. [Header definition](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L474), [File creation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_init.f90#L117)

| Field | Description | Unit |
| --- | --- | --- |
| `jday` | Day of year | n/a |
| `mon` | Month | n/a |
| `day` | Day of month | n/a |
| `yr` | Calendar year | n/a |
| `unit` | HRU identifier | n/a |
| `gis_id` | GIS identifier | n/a |
| `name` | Object name | n/a |
| [lab_min_p](modern-carbon-nitrogen/lab_min_p.md) | Labile-to-active mineral phosphorus transfer | kg P/ha |
| [act_sta_p](modern-carbon-nitrogen/act_sta_p.md) | Active-to-stable mineral phosphorus transfer | kg P/ha |
| [act_nit_n](modern-carbon-nitrogen/act_nit_n.md) | Active organic nitrogen mineralization | kg N/ha |
| [act_sta_n](modern-carbon-nitrogen/act_sta_n.md) | Active-to-stable organic nitrogen transfer | kg N/ha |
| [org_lab_p](modern-carbon-nitrogen/org_lab_p.md) | Organic-to-labile phosphorus transfer | kg P/ha |
| [rsd_hs_c](modern-carbon-nitrogen/rsd_hs_c.md) | Residue carbon transferred to humus | kg C/ha |
| [rsd_nitrorg_n](modern-carbon-nitrogen/rsd_nitrorg_n.md) | Residue nitrogen transferred to nitrate and organic pools | kg N/ha |
| [rsd_laborg_p](modern-carbon-nitrogen/rsd_laborg_p.md) | Residue phosphorus transferred to labile and organic pools | kg P/ha |

`rsd_nitrorg_n` is the literal printed heading.
