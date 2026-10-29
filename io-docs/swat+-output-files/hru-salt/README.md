# HRU Salt

HRU salt output reports salt stored in the soil profile and salt transferred by runoff, drainage, irrigation, deposition, applications, and plant uptake. Enable `hru_salt` in `print.prt`. Salt output is written only when salts are configured.

The files are `hru_salt_day`, `hru_salt_mon`, `hru_salt_yr`, and `hru_salt_aa`, with `.txt` and optional `.csv` variants. TXT files include explanatory preamble lines before the header. CSV files begin with the header row.

The printed headings use the ion order sulfate, calcium, magnesium, sodium, potassium, chloride, carbonate, and bicarbonate. The table groups related columns for readability, but every name shown is an exact output header. The units apply to daily, monthly, and yearly files; average-annual differences are explained below.

| Field | Description | Unit |
| --- | --- | --- |
| [jday](jday.md) | Day of year | n/a |
| [mon](mon.md) | Month | n/a |
| [day](day.md) | Day of month | n/a |
| [yr](yr.md) | Calendar year | n/a |
| [unit](unit.md) | HRU identifier | n/a |
| [gis_id](gis_id.md) | GIS identifier | n/a |
| [`soil_so4`](soil_so4.md), [`soil_ca`](soil_ca.md), [`soil_mg`](soil_mg.md), [`soil_na`](soil_na.md), [`soil_k`](soil_k.md), [`soil_cl`](soil_cl.md), [`soil_co3`](soil_co3.md), [`soil_hco3`](soil_hco3.md) | Salt stored in the soil profile | kg/ha |
| [`surq_so4`](surq_so4.md), [`surq_ca`](surq_ca.md), [`surq_mg`](surq_mg.md), [`surq_na`](surq_na.md), [`surq_k`](surq_k.md), [`surq_cl`](surq_cl.md), [`surq_co3`](surq_co3.md), [`surq_hco3`](surq_hco3.md) | Salt transported in surface runoff from soil to stream | kg/ha |
| [`latq_so4`](latq_so4.md), [`latq_ca`](latq_ca.md), [`latq_mg`](latq_mg.md), [`latq_na`](latq_na.md), [`latq_k`](latq_k.md), [`latq_cl`](latq_cl.md), [`latq_co3`](latq_co3.md), [`latq_hco3`](latq_hco3.md) | Salt transported in lateral soil flow to stream | kg/ha |
| [`urbq_so4`](urbq_so4.md), [`urbq_ca`](urbq_ca.md), [`urbq_mg`](urbq_mg.md), [`urbq_na`](urbq_na.md), [`urbq_k`](urbq_k.md), [`urbq_cl`](urbq_cl.md), [`urbq_co3`](urbq_co3.md), [`urbq_hco3`](urbq_hco3.md) | Salt transported in urban runoff to stream | kg/ha |
| [`wetq_so4`](wetq_so4.md), [`wetq_ca`](wetq_ca.md), [`wetq_mg`](wetq_mg.md), [`wetq_na`](wetq_na.md), [`wetq_k`](wetq_k.md), [`wetq_cl`](wetq_cl.md), [`wetq_co3`](wetq_co3.md), [`wetq_hco3`](wetq_hco3.md) | Salt transported in wetland runoff to stream | kg/ha |
| [`tile_so4`](tile_so4.md), [`tile_ca`](tile_ca.md), [`tile_mg`](tile_mg.md), [`tile_na`](tile_na.md), [`tile_k`](tile_k.md), [`tile_cl`](tile_cl.md), [`tile_co3`](tile_co3.md), [`tile_hco3`](tile_hco3.md) | Salt transported by tile drainage to stream | kg/ha |
| [`perc_so4`](perc_so4.md), [`perc_ca`](perc_ca.md), [`perc_mg`](perc_mg.md), [`perc_na`](perc_na.md), [`perc_k`](perc_k.md), [`perc_cl`](perc_cl.md), [`perc_co3`](perc_co3.md), [`perc_hco3`](perc_hco3.md) | Salt transported by deep percolation from soil to aquifer | kg/ha |
| [`gwup_so4`](gwup_so4.md), [`gwup_ca`](gwup_ca.md), [`gwup_mg`](gwup_mg.md), [`gwup_na`](gwup_na.md), [`gwup_k`](gwup_k.md), [`gwup_cl`](gwup_cl.md), [`gwup_co3`](gwup_co3.md), [`gwup_hco3`](gwup_hco3.md) | Groundwater salt transferred from aquifer to soil | kg/ha |
| [`wtsp_so4`](wtsp_so4.md), [`wtsp_ca`](wtsp_ca.md), [`wtsp_mg`](wtsp_mg.md), [`wtsp_na`](wtsp_na.md), [`wtsp_k`](wtsp_k.md), [`wtsp_cl`](wtsp_cl.md), [`wtsp_co3`](wtsp_co3.md), [`wtsp_hco3`](wtsp_hco3.md) | Salt transported by wetland seepage to soil | kg/ha |
| [`irsw_so4`](irsw_so4.md), [`irsw_ca`](irsw_ca.md), [`irsw_mg`](irsw_mg.md), [`irsw_na`](irsw_na.md), [`irsw_k`](irsw_k.md), [`irsw_cl`](irsw_cl.md), [`irsw_co3`](irsw_co3.md), [`irsw_hco3`](irsw_hco3.md) | Salt added by surface-water irrigation | kg/ha |
| [`irgw_so4`](irgw_so4.md), [`irgw_ca`](irgw_ca.md), [`irgw_mg`](irgw_mg.md), [`irgw_na`](irgw_na.md), [`irgw_k`](irgw_k.md), [`irgw_cl`](irgw_cl.md), [`irgw_co3`](irgw_co3.md), [`irgw_hco3`](irgw_hco3.md) | Salt added by groundwater irrigation | kg/ha |
| [`irwo_so4`](irwo_so4.md), [`irwo_ca`](irwo_ca.md), [`irwo_mg`](irwo_mg.md), [`irwo_na`](irwo_na.md), [`irwo_k`](irwo_k.md), [`irwo_cl`](irwo_cl.md), [`irwo_co3`](irwo_co3.md), [`irwo_hco3`](irwo_hco3.md) | Salt added by irrigation from an outside source | kg/ha |
| [`rain_so4`](rain_so4.md), [`rain_ca`](rain_ca.md), [`rain_mg`](rain_mg.md), [`rain_na`](rain_na.md), [`rain_k`](rain_k.md), [`rain_cl`](rain_cl.md), [`rain_co3`](rain_co3.md), [`rain_hco3`](rain_hco3.md) | Salt added by rainfall | kg/ha |
| [`dryd_so4`](dryd_so4.md), [`dryd_ca`](dryd_ca.md), [`dryd_mg`](dryd_mg.md), [`dryd_na`](dryd_na.md), [`dryd_k`](dryd_k.md), [`dryd_cl`](dryd_cl.md), [`dryd_co3`](dryd_co3.md), [`dryd_hco3`](dryd_hco3.md) | Salt added by dry deposition | kg/ha |
| [`road_so4`](road_so4.md), [`road_ca`](road_ca.md), [`road_mg`](road_mg.md), [`road_na`](road_na.md), [`road_k`](road_k.md), [`road_cl`](road_cl.md), [`road_co3`](road_co3.md), [`road_hco3`](road_hco3.md) | Salt added by road-salt application | kg/ha |
| [`fert_so4`](fert_so4.md), [`fert_ca`](fert_ca.md), [`fert_mg`](fert_mg.md), [`fert_na`](fert_na.md), [`fert_k`](fert_k.md), [`fert_cl`](fert_cl.md), [`fert_co3`](fert_co3.md), [`fert_hco3`](fert_hco3.md) | Salt added by fertilizer | kg/ha |
| [`amnd_so4`](amnd_so4.md), [`amnd_ca`](amnd_ca.md), [`amnd_mg`](amnd_mg.md), [`amnd_na`](amnd_na.md), [`amnd_k`](amnd_k.md), [`amnd_cl`](amnd_cl.md), [`amnd_co3`](amnd_co3.md), [`amnd_hco3`](amnd_hco3.md) | Salt added by soil amendments | kg/ha |
| [`uptk_so4`](uptk_so4.md), [`uptk_ca`](uptk_ca.md), [`uptk_mg`](uptk_mg.md), [`uptk_na`](uptk_na.md), [`uptk_k`](uptk_k.md), [`uptk_cl`](uptk_cl.md), [`uptk_co3`](uptk_co3.md), [`uptk_hco3`](uptk_hco3.md) | Salt removed by plant uptake | kg/ha |
| [`conc_so4`](conc_so4.md), [`conc_ca`](conc_ca.md), [`conc_mg`](conc_mg.md), [`conc_na`](conc_na.md), [`conc_k`](conc_k.md), [`conc_cl`](conc_cl.md), [`conc_co3`](conc_co3.md), [`conc_hco3`](conc_hco3.md) | Salt concentration in soil water, averaged over soil layers | g/m3 |
| [dssl_total](dssl_total.md) | Total salt-mineral dissolution, summed over soil layers | kg/ha |

{% hint style="warning" %}
In the inspected main version, the data rows omit the eight `gwup_` values even though those headings are printed. Values after `perc_hco3` are therefore shifted under the wrong headings and should not be interpreted by column name until the output mismatch is resolved.
{% endhint %}

Daily rows contain daily fluxes and current state values. Monthly and yearly rows accumulate fluxes while the `soil_` and `conc_` columns are averaged over the reporting period.

The average-annual row divides the ion-group values by the number of simulation years. Flux groups therefore represent average annual amounts in kg/ha/yr, while the `soil_` columns remain average states in kg/ha and the `conc_` columns remain concentrations in g/m3. The printed preamble labels the `soil_` columns as kg/ha/yr even though they are averaged states. `dssl_total` is not divided by the number of years and therefore remains cumulative across the simulation years, in kg/ha.
