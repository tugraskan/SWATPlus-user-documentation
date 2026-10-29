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
| [`soil_so4`](soil_so4.md) | Sulfate stored in the soil profile | kg/ha |
| [`soil_ca`](soil_ca.md) | Calcium stored in the soil profile | kg/ha |
| [`soil_mg`](soil_mg.md) | Magnesium stored in the soil profile | kg/ha |
| [`soil_na`](soil_na.md) | Sodium stored in the soil profile | kg/ha |
| [`soil_k`](soil_k.md) | Potassium stored in the soil profile | kg/ha |
| [`soil_cl`](soil_cl.md) | Chloride stored in the soil profile | kg/ha |
| [`soil_co3`](soil_co3.md) | Carbonate stored in the soil profile | kg/ha |
| [`soil_hco3`](soil_hco3.md) | Bicarbonate stored in the soil profile | kg/ha |
| [`surq_so4`](surq_so4.md) | Sulfate transported in surface runoff from soil to stream | kg/ha |
| [`surq_ca`](surq_ca.md) | Calcium transported in surface runoff from soil to stream | kg/ha |
| [`surq_mg`](surq_mg.md) | Magnesium transported in surface runoff from soil to stream | kg/ha |
| [`surq_na`](surq_na.md) | Sodium transported in surface runoff from soil to stream | kg/ha |
| [`surq_k`](surq_k.md) | Potassium transported in surface runoff from soil to stream | kg/ha |
| [`surq_cl`](surq_cl.md) | Chloride transported in surface runoff from soil to stream | kg/ha |
| [`surq_co3`](surq_co3.md) | Carbonate transported in surface runoff from soil to stream | kg/ha |
| [`surq_hco3`](surq_hco3.md) | Bicarbonate transported in surface runoff from soil to stream | kg/ha |
| [`latq_so4`](latq_so4.md) | Sulfate transported in lateral soil flow to stream | kg/ha |
| [`latq_ca`](latq_ca.md) | Calcium transported in lateral soil flow to stream | kg/ha |
| [`latq_mg`](latq_mg.md) | Magnesium transported in lateral soil flow to stream | kg/ha |
| [`latq_na`](latq_na.md) | Sodium transported in lateral soil flow to stream | kg/ha |
| [`latq_k`](latq_k.md) | Potassium transported in lateral soil flow to stream | kg/ha |
| [`latq_cl`](latq_cl.md) | Chloride transported in lateral soil flow to stream | kg/ha |
| [`latq_co3`](latq_co3.md) | Carbonate transported in lateral soil flow to stream | kg/ha |
| [`latq_hco3`](latq_hco3.md) | Bicarbonate transported in lateral soil flow to stream | kg/ha |
| [`urbq_so4`](urbq_so4.md) | Sulfate transported in urban runoff to stream | kg/ha |
| [`urbq_ca`](urbq_ca.md) | Calcium transported in urban runoff to stream | kg/ha |
| [`urbq_mg`](urbq_mg.md) | Magnesium transported in urban runoff to stream | kg/ha |
| [`urbq_na`](urbq_na.md) | Sodium transported in urban runoff to stream | kg/ha |
| [`urbq_k`](urbq_k.md) | Potassium transported in urban runoff to stream | kg/ha |
| [`urbq_cl`](urbq_cl.md) | Chloride transported in urban runoff to stream | kg/ha |
| [`urbq_co3`](urbq_co3.md) | Carbonate transported in urban runoff to stream | kg/ha |
| [`urbq_hco3`](urbq_hco3.md) | Bicarbonate transported in urban runoff to stream | kg/ha |
| [`wetq_so4`](wetq_so4.md) | Sulfate transported in wetland runoff to stream | kg/ha |
| [`wetq_ca`](wetq_ca.md) | Calcium transported in wetland runoff to stream | kg/ha |
| [`wetq_mg`](wetq_mg.md) | Magnesium transported in wetland runoff to stream | kg/ha |
| [`wetq_na`](wetq_na.md) | Sodium transported in wetland runoff to stream | kg/ha |
| [`wetq_k`](wetq_k.md) | Potassium transported in wetland runoff to stream | kg/ha |
| [`wetq_cl`](wetq_cl.md) | Chloride transported in wetland runoff to stream | kg/ha |
| [`wetq_co3`](wetq_co3.md) | Carbonate transported in wetland runoff to stream | kg/ha |
| [`wetq_hco3`](wetq_hco3.md) | Bicarbonate transported in wetland runoff to stream | kg/ha |
| [`tile_so4`](tile_so4.md) | Sulfate transported by tile drainage to stream | kg/ha |
| [`tile_ca`](tile_ca.md) | Calcium transported by tile drainage to stream | kg/ha |
| [`tile_mg`](tile_mg.md) | Magnesium transported by tile drainage to stream | kg/ha |
| [`tile_na`](tile_na.md) | Sodium transported by tile drainage to stream | kg/ha |
| [`tile_k`](tile_k.md) | Potassium transported by tile drainage to stream | kg/ha |
| [`tile_cl`](tile_cl.md) | Chloride transported by tile drainage to stream | kg/ha |
| [`tile_co3`](tile_co3.md) | Carbonate transported by tile drainage to stream | kg/ha |
| [`tile_hco3`](tile_hco3.md) | Bicarbonate transported by tile drainage to stream | kg/ha |
| [`perc_so4`](perc_so4.md) | Sulfate transported by deep percolation from soil to aquifer | kg/ha |
| [`perc_ca`](perc_ca.md) | Calcium transported by deep percolation from soil to aquifer | kg/ha |
| [`perc_mg`](perc_mg.md) | Magnesium transported by deep percolation from soil to aquifer | kg/ha |
| [`perc_na`](perc_na.md) | Sodium transported by deep percolation from soil to aquifer | kg/ha |
| [`perc_k`](perc_k.md) | Potassium transported by deep percolation from soil to aquifer | kg/ha |
| [`perc_cl`](perc_cl.md) | Chloride transported by deep percolation from soil to aquifer | kg/ha |
| [`perc_co3`](perc_co3.md) | Carbonate transported by deep percolation from soil to aquifer | kg/ha |
| [`perc_hco3`](perc_hco3.md) | Bicarbonate transported by deep percolation from soil to aquifer | kg/ha |
| [`gwup_so4`](gwup_so4.md) | Sulfate transferred from aquifer to soil | kg/ha |
| [`gwup_ca`](gwup_ca.md) | Calcium transferred from aquifer to soil | kg/ha |
| [`gwup_mg`](gwup_mg.md) | Magnesium transferred from aquifer to soil | kg/ha |
| [`gwup_na`](gwup_na.md) | Sodium transferred from aquifer to soil | kg/ha |
| [`gwup_k`](gwup_k.md) | Potassium transferred from aquifer to soil | kg/ha |
| [`gwup_cl`](gwup_cl.md) | Chloride transferred from aquifer to soil | kg/ha |
| [`gwup_co3`](gwup_co3.md) | Carbonate transferred from aquifer to soil | kg/ha |
| [`gwup_hco3`](gwup_hco3.md) | Bicarbonate transferred from aquifer to soil | kg/ha |
| [`wtsp_so4`](wtsp_so4.md) | Sulfate transported by wetland seepage to soil | kg/ha |
| [`wtsp_ca`](wtsp_ca.md) | Calcium transported by wetland seepage to soil | kg/ha |
| [`wtsp_mg`](wtsp_mg.md) | Magnesium transported by wetland seepage to soil | kg/ha |
| [`wtsp_na`](wtsp_na.md) | Sodium transported by wetland seepage to soil | kg/ha |
| [`wtsp_k`](wtsp_k.md) | Potassium transported by wetland seepage to soil | kg/ha |
| [`wtsp_cl`](wtsp_cl.md) | Chloride transported by wetland seepage to soil | kg/ha |
| [`wtsp_co3`](wtsp_co3.md) | Carbonate transported by wetland seepage to soil | kg/ha |
| [`wtsp_hco3`](wtsp_hco3.md) | Bicarbonate transported by wetland seepage to soil | kg/ha |
| [`irsw_so4`](irsw_so4.md) | Sulfate added by surface-water irrigation | kg/ha |
| [`irsw_ca`](irsw_ca.md) | Calcium added by surface-water irrigation | kg/ha |
| [`irsw_mg`](irsw_mg.md) | Magnesium added by surface-water irrigation | kg/ha |
| [`irsw_na`](irsw_na.md) | Sodium added by surface-water irrigation | kg/ha |
| [`irsw_k`](irsw_k.md) | Potassium added by surface-water irrigation | kg/ha |
| [`irsw_cl`](irsw_cl.md) | Chloride added by surface-water irrigation | kg/ha |
| [`irsw_co3`](irsw_co3.md) | Carbonate added by surface-water irrigation | kg/ha |
| [`irsw_hco3`](irsw_hco3.md) | Bicarbonate added by surface-water irrigation | kg/ha |
| [`irgw_so4`](irgw_so4.md) | Sulfate added by groundwater irrigation | kg/ha |
| [`irgw_ca`](irgw_ca.md) | Calcium added by groundwater irrigation | kg/ha |
| [`irgw_mg`](irgw_mg.md) | Magnesium added by groundwater irrigation | kg/ha |
| [`irgw_na`](irgw_na.md) | Sodium added by groundwater irrigation | kg/ha |
| [`irgw_k`](irgw_k.md) | Potassium added by groundwater irrigation | kg/ha |
| [`irgw_cl`](irgw_cl.md) | Chloride added by groundwater irrigation | kg/ha |
| [`irgw_co3`](irgw_co3.md) | Carbonate added by groundwater irrigation | kg/ha |
| [`irgw_hco3`](irgw_hco3.md) | Bicarbonate added by groundwater irrigation | kg/ha |
| [`irwo_so4`](irwo_so4.md) | Sulfate added by irrigation from an outside source | kg/ha |
| [`irwo_ca`](irwo_ca.md) | Calcium added by irrigation from an outside source | kg/ha |
| [`irwo_mg`](irwo_mg.md) | Magnesium added by irrigation from an outside source | kg/ha |
| [`irwo_na`](irwo_na.md) | Sodium added by irrigation from an outside source | kg/ha |
| [`irwo_k`](irwo_k.md) | Potassium added by irrigation from an outside source | kg/ha |
| [`irwo_cl`](irwo_cl.md) | Chloride added by irrigation from an outside source | kg/ha |
| [`irwo_co3`](irwo_co3.md) | Carbonate added by irrigation from an outside source | kg/ha |
| [`irwo_hco3`](irwo_hco3.md) | Bicarbonate added by irrigation from an outside source | kg/ha |
| [`rain_so4`](rain_so4.md) | Sulfate added by rainfall | kg/ha |
| [`rain_ca`](rain_ca.md) | Calcium added by rainfall | kg/ha |
| [`rain_mg`](rain_mg.md) | Magnesium added by rainfall | kg/ha |
| [`rain_na`](rain_na.md) | Sodium added by rainfall | kg/ha |
| [`rain_k`](rain_k.md) | Potassium added by rainfall | kg/ha |
| [`rain_cl`](rain_cl.md) | Chloride added by rainfall | kg/ha |
| [`rain_co3`](rain_co3.md) | Carbonate added by rainfall | kg/ha |
| [`rain_hco3`](rain_hco3.md) | Bicarbonate added by rainfall | kg/ha |
| [`dryd_so4`](dryd_so4.md) | Sulfate added by dry deposition | kg/ha |
| [`dryd_ca`](dryd_ca.md) | Calcium added by dry deposition | kg/ha |
| [`dryd_mg`](dryd_mg.md) | Magnesium added by dry deposition | kg/ha |
| [`dryd_na`](dryd_na.md) | Sodium added by dry deposition | kg/ha |
| [`dryd_k`](dryd_k.md) | Potassium added by dry deposition | kg/ha |
| [`dryd_cl`](dryd_cl.md) | Chloride added by dry deposition | kg/ha |
| [`dryd_co3`](dryd_co3.md) | Carbonate added by dry deposition | kg/ha |
| [`dryd_hco3`](dryd_hco3.md) | Bicarbonate added by dry deposition | kg/ha |
| [`road_so4`](road_so4.md) | Sulfate added by road-salt application | kg/ha |
| [`road_ca`](road_ca.md) | Calcium added by road-salt application | kg/ha |
| [`road_mg`](road_mg.md) | Magnesium added by road-salt application | kg/ha |
| [`road_na`](road_na.md) | Sodium added by road-salt application | kg/ha |
| [`road_k`](road_k.md) | Potassium added by road-salt application | kg/ha |
| [`road_cl`](road_cl.md) | Chloride added by road-salt application | kg/ha |
| [`road_co3`](road_co3.md) | Carbonate added by road-salt application | kg/ha |
| [`road_hco3`](road_hco3.md) | Bicarbonate added by road-salt application | kg/ha |
| [`fert_so4`](fert_so4.md) | Sulfate added by fertilizer | kg/ha |
| [`fert_ca`](fert_ca.md) | Calcium added by fertilizer | kg/ha |
| [`fert_mg`](fert_mg.md) | Magnesium added by fertilizer | kg/ha |
| [`fert_na`](fert_na.md) | Sodium added by fertilizer | kg/ha |
| [`fert_k`](fert_k.md) | Potassium added by fertilizer | kg/ha |
| [`fert_cl`](fert_cl.md) | Chloride added by fertilizer | kg/ha |
| [`fert_co3`](fert_co3.md) | Carbonate added by fertilizer | kg/ha |
| [`fert_hco3`](fert_hco3.md) | Bicarbonate added by fertilizer | kg/ha |
| [`amnd_so4`](amnd_so4.md) | Sulfate added by soil amendments | kg/ha |
| [`amnd_ca`](amnd_ca.md) | Calcium added by soil amendments | kg/ha |
| [`amnd_mg`](amnd_mg.md) | Magnesium added by soil amendments | kg/ha |
| [`amnd_na`](amnd_na.md) | Sodium added by soil amendments | kg/ha |
| [`amnd_k`](amnd_k.md) | Potassium added by soil amendments | kg/ha |
| [`amnd_cl`](amnd_cl.md) | Chloride added by soil amendments | kg/ha |
| [`amnd_co3`](amnd_co3.md) | Carbonate added by soil amendments | kg/ha |
| [`amnd_hco3`](amnd_hco3.md) | Bicarbonate added by soil amendments | kg/ha |
| [`uptk_so4`](uptk_so4.md) | Sulfate removed by plant uptake | kg/ha |
| [`uptk_ca`](uptk_ca.md) | Calcium removed by plant uptake | kg/ha |
| [`uptk_mg`](uptk_mg.md) | Magnesium removed by plant uptake | kg/ha |
| [`uptk_na`](uptk_na.md) | Sodium removed by plant uptake | kg/ha |
| [`uptk_k`](uptk_k.md) | Potassium removed by plant uptake | kg/ha |
| [`uptk_cl`](uptk_cl.md) | Chloride removed by plant uptake | kg/ha |
| [`uptk_co3`](uptk_co3.md) | Carbonate removed by plant uptake | kg/ha |
| [`uptk_hco3`](uptk_hco3.md) | Bicarbonate removed by plant uptake | kg/ha |
| [`conc_so4`](conc_so4.md) | Sulfate concentration in soil water, averaged over soil layers | g/m3 |
| [`conc_ca`](conc_ca.md) | Calcium concentration in soil water, averaged over soil layers | g/m3 |
| [`conc_mg`](conc_mg.md) | Magnesium concentration in soil water, averaged over soil layers | g/m3 |
| [`conc_na`](conc_na.md) | Sodium concentration in soil water, averaged over soil layers | g/m3 |
| [`conc_k`](conc_k.md) | Potassium concentration in soil water, averaged over soil layers | g/m3 |
| [`conc_cl`](conc_cl.md) | Chloride concentration in soil water, averaged over soil layers | g/m3 |
| [`conc_co3`](conc_co3.md) | Carbonate concentration in soil water, averaged over soil layers | g/m3 |
| [`conc_hco3`](conc_hco3.md) | Bicarbonate concentration in soil water, averaged over soil layers | g/m3 |
| [dssl_total](dssl_total.md) | Total salt-mineral dissolution, summed over soil layers | kg/ha |

{% hint style="warning" %}
In the inspected main version, the data rows omit the eight `gwup_` values even though those headings are printed. Values after `perc_hco3` are therefore shifted under the wrong headings and should not be interpreted by column name until the output mismatch is resolved.
{% endhint %}

Daily rows contain daily fluxes and current state values. Monthly and yearly rows accumulate fluxes while the `soil_` and `conc_` columns are averaged over the reporting period.

The average-annual row divides the ion-group values by the number of simulation years. Flux groups therefore represent average annual amounts in kg/ha/yr, while the `soil_` columns remain average states in kg/ha and the `conc_` columns remain concentrations in g/m3. The printed preamble labels the `soil_` columns as kg/ha/yr even though they are averaged states. `dssl_total` is not divided by the number of years and therefore remains cumulative across the simulation years, in kg/ha.
