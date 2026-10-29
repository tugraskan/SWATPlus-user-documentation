# HRU Salt

HRU salt output reports salt stored in the soil profile and salt transferred by runoff, drainage, irrigation, deposition, applications, and plant uptake. Enable `hru_salt` in `print.prt`. Salt output is written only when salts are configured.

The files are `hru_salt_day`, `hru_salt_mon`, `hru_salt_yr`, and `hru_salt_aa`, with `.txt` and optional `.csv` variants. TXT files include explanatory preamble lines before the header. CSV files begin with the header row.

The printed headings use the ion order sulfate, calcium, magnesium, sodium, potassium, chloride, carbonate, and bicarbonate. The table groups related columns for readability, but every name shown is an exact output header. The units apply to daily, monthly, and yearly files; average-annual differences are explained below.

| Field | Description | Unit |
| --- | --- | --- |
| [jday](hru-salt/jday.md) | Day of year | n/a |
| [mon](hru-salt/mon.md) | Month | n/a |
| [day](hru-salt/day.md) | Day of month | n/a |
| [yr](hru-salt/yr.md) | Calendar year | n/a |
| [unit](hru-salt/unit.md) | HRU identifier | n/a |
| [gis_id](hru-salt/gis_id.md) | GIS identifier | n/a |
| [`soil_so4`](hru-salt/soil_so4.md), [`soil_ca`](hru-salt/soil_ca.md), [`soil_mg`](hru-salt/soil_mg.md), [`soil_na`](hru-salt/soil_na.md), [`soil_k`](hru-salt/soil_k.md), [`soil_cl`](hru-salt/soil_cl.md), [`soil_co3`](hru-salt/soil_co3.md), [`soil_hco3`](hru-salt/soil_hco3.md) | Salt stored in the soil profile | kg/ha |
| [`surq_so4`](hru-salt/surq_so4.md), [`surq_ca`](hru-salt/surq_ca.md), [`surq_mg`](hru-salt/surq_mg.md), [`surq_na`](hru-salt/surq_na.md), [`surq_k`](hru-salt/surq_k.md), [`surq_cl`](hru-salt/surq_cl.md), [`surq_co3`](hru-salt/surq_co3.md), [`surq_hco3`](hru-salt/surq_hco3.md) | Salt transported in surface runoff from soil to stream | kg/ha |
| [`latq_so4`](hru-salt/latq_so4.md), [`latq_ca`](hru-salt/latq_ca.md), [`latq_mg`](hru-salt/latq_mg.md), [`latq_na`](hru-salt/latq_na.md), [`latq_k`](hru-salt/latq_k.md), [`latq_cl`](hru-salt/latq_cl.md), [`latq_co3`](hru-salt/latq_co3.md), [`latq_hco3`](hru-salt/latq_hco3.md) | Salt transported in lateral soil flow to stream | kg/ha |
| [`urbq_so4`](hru-salt/urbq_so4.md), [`urbq_ca`](hru-salt/urbq_ca.md), [`urbq_mg`](hru-salt/urbq_mg.md), [`urbq_na`](hru-salt/urbq_na.md), [`urbq_k`](hru-salt/urbq_k.md), [`urbq_cl`](hru-salt/urbq_cl.md), [`urbq_co3`](hru-salt/urbq_co3.md), [`urbq_hco3`](hru-salt/urbq_hco3.md) | Salt transported in urban runoff to stream | kg/ha |
| [`wetq_so4`](hru-salt/wetq_so4.md), [`wetq_ca`](hru-salt/wetq_ca.md), [`wetq_mg`](hru-salt/wetq_mg.md), [`wetq_na`](hru-salt/wetq_na.md), [`wetq_k`](hru-salt/wetq_k.md), [`wetq_cl`](hru-salt/wetq_cl.md), [`wetq_co3`](hru-salt/wetq_co3.md), [`wetq_hco3`](hru-salt/wetq_hco3.md) | Salt transported in wetland runoff to stream | kg/ha |
| [`tile_so4`](hru-salt/tile_so4.md), [`tile_ca`](hru-salt/tile_ca.md), [`tile_mg`](hru-salt/tile_mg.md), [`tile_na`](hru-salt/tile_na.md), [`tile_k`](hru-salt/tile_k.md), [`tile_cl`](hru-salt/tile_cl.md), [`tile_co3`](hru-salt/tile_co3.md), [`tile_hco3`](hru-salt/tile_hco3.md) | Salt transported by tile drainage to stream | kg/ha |
| [`perc_so4`](hru-salt/perc_so4.md), [`perc_ca`](hru-salt/perc_ca.md), [`perc_mg`](hru-salt/perc_mg.md), [`perc_na`](hru-salt/perc_na.md), [`perc_k`](hru-salt/perc_k.md), [`perc_cl`](hru-salt/perc_cl.md), [`perc_co3`](hru-salt/perc_co3.md), [`perc_hco3`](hru-salt/perc_hco3.md) | Salt transported by deep percolation from soil to aquifer | kg/ha |
| [`gwup_so4`](hru-salt/gwup_so4.md), [`gwup_ca`](hru-salt/gwup_ca.md), [`gwup_mg`](hru-salt/gwup_mg.md), [`gwup_na`](hru-salt/gwup_na.md), [`gwup_k`](hru-salt/gwup_k.md), [`gwup_cl`](hru-salt/gwup_cl.md), [`gwup_co3`](hru-salt/gwup_co3.md), [`gwup_hco3`](hru-salt/gwup_hco3.md) | Groundwater salt transferred from aquifer to soil | kg/ha |
| [`wtsp_so4`](hru-salt/wtsp_so4.md), [`wtsp_ca`](hru-salt/wtsp_ca.md), [`wtsp_mg`](hru-salt/wtsp_mg.md), [`wtsp_na`](hru-salt/wtsp_na.md), [`wtsp_k`](hru-salt/wtsp_k.md), [`wtsp_cl`](hru-salt/wtsp_cl.md), [`wtsp_co3`](hru-salt/wtsp_co3.md), [`wtsp_hco3`](hru-salt/wtsp_hco3.md) | Salt transported by wetland seepage to soil | kg/ha |
| [`irsw_so4`](hru-salt/irsw_so4.md), [`irsw_ca`](hru-salt/irsw_ca.md), [`irsw_mg`](hru-salt/irsw_mg.md), [`irsw_na`](hru-salt/irsw_na.md), [`irsw_k`](hru-salt/irsw_k.md), [`irsw_cl`](hru-salt/irsw_cl.md), [`irsw_co3`](hru-salt/irsw_co3.md), [`irsw_hco3`](hru-salt/irsw_hco3.md) | Salt added by surface-water irrigation | kg/ha |
| [`irgw_so4`](hru-salt/irgw_so4.md), [`irgw_ca`](hru-salt/irgw_ca.md), [`irgw_mg`](hru-salt/irgw_mg.md), [`irgw_na`](hru-salt/irgw_na.md), [`irgw_k`](hru-salt/irgw_k.md), [`irgw_cl`](hru-salt/irgw_cl.md), [`irgw_co3`](hru-salt/irgw_co3.md), [`irgw_hco3`](hru-salt/irgw_hco3.md) | Salt added by groundwater irrigation | kg/ha |
| [`irwo_so4`](hru-salt/irwo_so4.md), [`irwo_ca`](hru-salt/irwo_ca.md), [`irwo_mg`](hru-salt/irwo_mg.md), [`irwo_na`](hru-salt/irwo_na.md), [`irwo_k`](hru-salt/irwo_k.md), [`irwo_cl`](hru-salt/irwo_cl.md), [`irwo_co3`](hru-salt/irwo_co3.md), [`irwo_hco3`](hru-salt/irwo_hco3.md) | Salt added by irrigation from an outside source | kg/ha |
| [`rain_so4`](hru-salt/rain_so4.md), [`rain_ca`](hru-salt/rain_ca.md), [`rain_mg`](hru-salt/rain_mg.md), [`rain_na`](hru-salt/rain_na.md), [`rain_k`](hru-salt/rain_k.md), [`rain_cl`](hru-salt/rain_cl.md), [`rain_co3`](hru-salt/rain_co3.md), [`rain_hco3`](hru-salt/rain_hco3.md) | Salt added by rainfall | kg/ha |
| [`dryd_so4`](hru-salt/dryd_so4.md), [`dryd_ca`](hru-salt/dryd_ca.md), [`dryd_mg`](hru-salt/dryd_mg.md), [`dryd_na`](hru-salt/dryd_na.md), [`dryd_k`](hru-salt/dryd_k.md), [`dryd_cl`](hru-salt/dryd_cl.md), [`dryd_co3`](hru-salt/dryd_co3.md), [`dryd_hco3`](hru-salt/dryd_hco3.md) | Salt added by dry deposition | kg/ha |
| [`road_so4`](hru-salt/road_so4.md), [`road_ca`](hru-salt/road_ca.md), [`road_mg`](hru-salt/road_mg.md), [`road_na`](hru-salt/road_na.md), [`road_k`](hru-salt/road_k.md), [`road_cl`](hru-salt/road_cl.md), [`road_co3`](hru-salt/road_co3.md), [`road_hco3`](hru-salt/road_hco3.md) | Salt added by road-salt application | kg/ha |
| [`fert_so4`](hru-salt/fert_so4.md), [`fert_ca`](hru-salt/fert_ca.md), [`fert_mg`](hru-salt/fert_mg.md), [`fert_na`](hru-salt/fert_na.md), [`fert_k`](hru-salt/fert_k.md), [`fert_cl`](hru-salt/fert_cl.md), [`fert_co3`](hru-salt/fert_co3.md), [`fert_hco3`](hru-salt/fert_hco3.md) | Salt added by fertilizer | kg/ha |
| [`amnd_so4`](hru-salt/amnd_so4.md), [`amnd_ca`](hru-salt/amnd_ca.md), [`amnd_mg`](hru-salt/amnd_mg.md), [`amnd_na`](hru-salt/amnd_na.md), [`amnd_k`](hru-salt/amnd_k.md), [`amnd_cl`](hru-salt/amnd_cl.md), [`amnd_co3`](hru-salt/amnd_co3.md), [`amnd_hco3`](hru-salt/amnd_hco3.md) | Salt added by soil amendments | kg/ha |
| [`uptk_so4`](hru-salt/uptk_so4.md), [`uptk_ca`](hru-salt/uptk_ca.md), [`uptk_mg`](hru-salt/uptk_mg.md), [`uptk_na`](hru-salt/uptk_na.md), [`uptk_k`](hru-salt/uptk_k.md), [`uptk_cl`](hru-salt/uptk_cl.md), [`uptk_co3`](hru-salt/uptk_co3.md), [`uptk_hco3`](hru-salt/uptk_hco3.md) | Salt removed by plant uptake | kg/ha |
| [`conc_so4`](hru-salt/conc_so4.md), [`conc_ca`](hru-salt/conc_ca.md), [`conc_mg`](hru-salt/conc_mg.md), [`conc_na`](hru-salt/conc_na.md), [`conc_k`](hru-salt/conc_k.md), [`conc_cl`](hru-salt/conc_cl.md), [`conc_co3`](hru-salt/conc_co3.md), [`conc_hco3`](hru-salt/conc_hco3.md) | Salt concentration in soil water, averaged over soil layers | g/m3 |
| [dssl_total](hru-salt/dssl_total.md) | Total salt-mineral dissolution, summed over soil layers | kg/ha |

{% hint style="warning" %}
In the inspected main version, the data rows omit the eight `gwup_` values even though those headings are printed. Values after `perc_hco3` are therefore shifted under the wrong headings and should not be interpreted by column name until the output mismatch is resolved.
{% endhint %}

Daily rows contain daily fluxes and current state values. Monthly and yearly rows accumulate fluxes while the `soil_` and `conc_` columns are averaged over the reporting period.

The average-annual row divides the ion-group values by the number of simulation years. Flux groups therefore represent average annual amounts in kg/ha/yr, while the `soil_` columns remain average states in kg/ha and the `conc_` columns remain concentrations in g/m3. The printed preamble labels the `soil_` columns as kg/ha/yr even though they are averaged states. `dssl_total` is not divided by the number of years and therefore remains cumulative across the simulation years, in kg/ha.
