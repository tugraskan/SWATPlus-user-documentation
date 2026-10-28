# HRU Salt

HRU salt output reports salt stored in the soil profile and salt transferred by runoff, drainage, irrigation, deposition, applications, and plant uptake. Enable `hru_salt` in `print.prt`. Salt output is written only when salts are configured.

The files are `hru_salt_day`, `hru_salt_mon`, `hru_salt_yr`, and `hru_salt_aa`, with `.txt` and optional `.csv` variants. TXT files include explanatory preamble lines before the header. CSV files begin with the header row.

The printed headings use the ion order sulfate, calcium, magnesium, sodium, potassium, chloride, carbonate, and bicarbonate. The table groups related columns for readability, but every name shown is an exact output header. The units apply to daily, monthly, and yearly files; average-annual differences are explained below.

| Field | Description | Unit |
| --- | --- | --- |
| jday | Day of year | n/a |
| mon | Month | n/a |
| day | Day of month | n/a |
| yr | Calendar year | n/a |
| unit | HRU identifier | n/a |
| gis_id | GIS identifier | n/a |
| `soil_so4`, `soil_ca`, `soil_mg`, `soil_na`, `soil_k`, `soil_cl`, `soil_co3`, `soil_hco3` | Salt stored in the soil profile | kg/ha |
| `surq_so4`, `surq_ca`, `surq_mg`, `surq_na`, `surq_k`, `surq_cl`, `surq_co3`, `surq_hco3` | Salt transported in surface runoff from soil to stream | kg/ha |
| `latq_so4`, `latq_ca`, `latq_mg`, `latq_na`, `latq_k`, `latq_cl`, `latq_co3`, `latq_hco3` | Salt transported in lateral soil flow to stream | kg/ha |
| `urbq_so4`, `urbq_ca`, `urbq_mg`, `urbq_na`, `urbq_k`, `urbq_cl`, `urbq_co3`, `urbq_hco3` | Salt transported in urban runoff to stream | kg/ha |
| `wetq_so4`, `wetq_ca`, `wetq_mg`, `wetq_na`, `wetq_k`, `wetq_cl`, `wetq_co3`, `wetq_hco3` | Salt transported in wetland runoff to stream | kg/ha |
| `tile_so4`, `tile_ca`, `tile_mg`, `tile_na`, `tile_k`, `tile_cl`, `tile_co3`, `tile_hco3` | Salt transported by tile drainage to stream | kg/ha |
| `perc_so4`, `perc_ca`, `perc_mg`, `perc_na`, `perc_k`, `perc_cl`, `perc_co3`, `perc_hco3` | Salt transported by deep percolation from soil to aquifer | kg/ha |
| `gwup_so4`, `gwup_ca`, `gwup_mg`, `gwup_na`, `gwup_k`, `gwup_cl`, `gwup_co3`, `gwup_hco3` | Groundwater salt transferred from aquifer to soil | kg/ha |
| `wtsp_so4`, `wtsp_ca`, `wtsp_mg`, `wtsp_na`, `wtsp_k`, `wtsp_cl`, `wtsp_co3`, `wtsp_hco3` | Salt transported by wetland seepage to soil | kg/ha |
| `irsw_so4`, `irsw_ca`, `irsw_mg`, `irsw_na`, `irsw_k`, `irsw_cl`, `irsw_co3`, `irsw_hco3` | Salt added by surface-water irrigation | kg/ha |
| `irgw_so4`, `irgw_ca`, `irgw_mg`, `irgw_na`, `irgw_k`, `irgw_cl`, `irgw_co3`, `irgw_hco3` | Salt added by groundwater irrigation | kg/ha |
| `irwo_so4`, `irwo_ca`, `irwo_mg`, `irwo_na`, `irwo_k`, `irwo_cl`, `irwo_co3`, `irwo_hco3` | Salt added by irrigation from an outside source | kg/ha |
| `rain_so4`, `rain_ca`, `rain_mg`, `rain_na`, `rain_k`, `rain_cl`, `rain_co3`, `rain_hco3` | Salt added by rainfall | kg/ha |
| `dryd_so4`, `dryd_ca`, `dryd_mg`, `dryd_na`, `dryd_k`, `dryd_cl`, `dryd_co3`, `dryd_hco3` | Salt added by dry deposition | kg/ha |
| `road_so4`, `road_ca`, `road_mg`, `road_na`, `road_k`, `road_cl`, `road_co3`, `road_hco3` | Salt added by road-salt application | kg/ha |
| `fert_so4`, `fert_ca`, `fert_mg`, `fert_na`, `fert_k`, `fert_cl`, `fert_co3`, `fert_hco3` | Salt added by fertilizer | kg/ha |
| `amnd_so4`, `amnd_ca`, `amnd_mg`, `amnd_na`, `amnd_k`, `amnd_cl`, `amnd_co3`, `amnd_hco3` | Salt added by soil amendments | kg/ha |
| `uptk_so4`, `uptk_ca`, `uptk_mg`, `uptk_na`, `uptk_k`, `uptk_cl`, `uptk_co3`, `uptk_hco3` | Salt removed by plant uptake | kg/ha |
| `conc_so4`, `conc_ca`, `conc_mg`, `conc_na`, `conc_k`, `conc_cl`, `conc_co3`, `conc_hco3` | Salt concentration in soil water, averaged over soil layers | g/m3 |
| dssl_total | Total salt-mineral dissolution, summed over soil layers | kg/ha |

{% hint style="warning" %}
In the inspected main version, the data rows omit the eight `gwup_` values even though those headings are printed. Values after `perc_hco3` are therefore shifted under the wrong headings and should not be interpreted by column name until the output mismatch is resolved.
{% endhint %}

Daily rows contain daily fluxes and current state values. Monthly and yearly rows accumulate fluxes while the `soil_` and `conc_` columns are averaged over the reporting period.

The average-annual row divides the ion-group values by the number of simulation years. Flux groups therefore represent average annual amounts in kg/ha/yr, while the `soil_` columns remain average states in kg/ha and the `conc_` columns remain concentrations in g/m3. The printed preamble labels the `soil_` columns as kg/ha/yr even though they are averaged states. `dssl_total` is not divided by the number of years and therefore remains cumulative across the simulation years, in kg/ha.
