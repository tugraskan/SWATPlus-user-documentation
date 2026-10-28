# HRU Salt

HRU salt output reports salt stored in the soil profile and salt transferred by runoff, drainage, irrigation, deposition, applications, and plant uptake. Enable `hru_salt` in `print.prt`. Salt output is written only when salts are configured.

The files are `hru_salt_day`, `hru_salt_mon`, `hru_salt_yr`, and `hru_salt_aa`, with `.txt` and optional `.csv` variants. TXT files include explanatory preamble lines before the header. CSV files begin with the header row.

The salt-ion suffixes used in the printed headings are `so4`, `ca`, `mg`, `na`, `k`, `cl`, `co3`, and `hco3`. Each field pattern below expands to those eight printed suffixes in that order. The units in the table apply to daily, monthly, and yearly files; average-annual differences are explained below.

| Field | Description | Unit |
| --- | --- | --- |
| jday | Day of year | n/a |
| mon | Month | n/a |
| day | Day of month | n/a |
| yr | Calendar year | n/a |
| unit | HRU identifier | n/a |
| gis_id | GIS identifier | n/a |
| soil_* | Salt stored in the soil profile | kg/ha |
| surq_* | Salt transported in surface runoff from soil to stream | kg/ha |
| latq_* | Salt transported in lateral soil flow to stream | kg/ha |
| urbq_* | Salt transported in urban runoff to stream | kg/ha |
| wetq_* | Salt transported in wetland runoff to stream | kg/ha |
| tile_* | Salt transported by tile drainage to stream | kg/ha |
| perc_* | Salt transported by deep percolation from soil to aquifer | kg/ha |
| gwup_* | Groundwater salt transferred from aquifer to soil | kg/ha |
| wtsp_* | Salt transported by wetland seepage to soil | kg/ha |
| irsw_* | Salt added by surface-water irrigation | kg/ha |
| irgw_* | Salt added by groundwater irrigation | kg/ha |
| irwo_* | Salt added by irrigation from an outside source | kg/ha |
| rain_* | Salt added by rainfall | kg/ha |
| dryd_* | Salt added by dry deposition | kg/ha |
| road_* | Salt added by road-salt application | kg/ha |
| fert_* | Salt added by fertilizer | kg/ha |
| amnd_* | Salt added by soil amendments | kg/ha |
| uptk_* | Salt removed by plant uptake | kg/ha |
| conc_* | Salt concentration in soil water, averaged over soil layers | g/m3 |
| dssl_total | Total salt-mineral dissolution, summed over soil layers | kg/ha |

{% hint style="warning" %}
In the inspected main version, the data rows omit the eight `gwup_*` values even though those headings are printed. Values after `perc_*` are therefore shifted under the wrong headings and should not be interpreted by column name until the output mismatch is resolved.
{% endhint %}

Daily rows contain daily fluxes and current state values. Monthly and yearly rows accumulate fluxes while `soil_*` and `conc_*` are averaged over the reporting period.

The average-annual row divides the ion-group values by the number of simulation years. Flux groups therefore represent average annual amounts in kg/ha/yr, while `soil_*` remains an average state in kg/ha and `conc_*` remains a concentration in g/m3. The printed preamble labels `soil_*` as kg/ha/yr even though it is an averaged state. `dssl_total` is not divided by the number of years and therefore remains cumulative across the simulation years, in kg/ha.
