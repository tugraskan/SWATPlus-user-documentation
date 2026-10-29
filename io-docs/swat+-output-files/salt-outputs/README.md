# Salt Outputs

SWAT+ can report salt balances for the basin, routing units, HRUs, channels, aquifers, reservoirs, and wetlands. These files are produced only when the salt module is configured and the corresponding print option is enabled. Daily, monthly, yearly, and average-annual files use the suffixes `_day`, `_mon`, `_yr`, and `_aa`; TXT and CSV variants share the same data headings.

The salt ions always appear in this order: sulfate (`so4`), calcium (`ca`), magnesium (`mg`), sodium (`na`), potassium (`k`), chloride (`cl`), carbonate (`co3`), and bicarbonate (`hco3`). Every name in the Field column below is an exact printed heading.

Unless a section states otherwise, daily, monthly, and yearly mass fields are printed in kg for the reporting interval. In average-annual files, the printed units row labels flux fields as kg/yr. Stored mass remains a state value, although some average-annual preambles also print kg/yr for those headings; the tables below reproduce the source-defined output rather than reinterpreting it. Concentrations are printed in g/m3.

The common identifying headings are `jday`, `mon`, `day`, `yr`, `unit`, and `gis_id`. Basin salt output instead begins with `yr`, `mo`, and `jday`.

## Basin salt balance

The files are `basin_salt_day`, `basin_salt_mon`, `basin_salt_yr`, and `basin_salt_aa` with `.txt` and `.csv` variants. Each mass-balance heading represents the total of all eight ions.

| Field | Description | Unit |
| --- | --- | --- |
| [`lat_kg`](lat_kg.md) | Salt reaching streams through lateral flow | kg |
| [`gw_kg`](gw_kg.md) | Salt reaching streams through groundwater | kg |
| [`sur_kg`](sur_kg.md) | Salt reaching streams through surface runoff | kg |
| [`urb_kg`](urb_kg.md) | Salt reaching streams through urban runoff | kg |
| [`wet_kg`](wet_kg.md) | Salt reaching streams through wetland outflow | kg |
| [`tile_kg`](tile_kg.md) | Salt reaching streams through tile drainage | kg |
| [`perc_kg`](perc_kg.md) | Salt transferred by percolation | kg |
| [`gwup_kg`](gwup_kg.md) | Salt transferred from groundwater to soil | kg |
| [`wtsp_kg`](wtsp_kg.md) | Salt transferred by wetland seepage | kg |
| [`irsw_kg`](irsw_kg.md) | Salt added by surface-water irrigation | kg |
| [`irgw_kg`](irgw_kg.md) | Salt added by groundwater irrigation | kg |
| [`irwo_kg`](irwo_kg.md) | Salt added by outside-source irrigation | kg |
| [`rain_kg`](rain_kg.md) | Salt added by rain | kg |
| [`dryd_kg`](dryd_kg.md) | Salt added by dry deposition | kg |
| [`road_kg`](road_kg.md) | Salt added by road-salt application | kg |
| [`fert_kg`](fert_kg.md) | Salt added by fertilizer | kg |
| [`amnd_kg`](amnd_kg.md) | Salt added by amendments | kg |
| [`uptk_kg`](uptk_kg.md) | Salt removed by plant uptake | kg |
| [`ptso_kg`](ptso_kg.md) | Point-source salt entering the basin | kg |
| [`ptout_kg`](ptout_kg.md) | Point-source salt leaving the basin | kg |
| [`rchg_kg`](rchg_kg.md) | Salt entering aquifers with recharge | kg |
| [`seep_kg`](seep_kg.md) | Salt leaving aquifers through seepage | kg |
| [`dssl_kg`](dssl_kg.md) | Mineral dissolution in soils | kg |
| [`dsaq_kg`](dsaq_kg.md) | Mineral dissolution in aquifers | kg |
| [`soilds_kg`](soilds_kg.md) | Dissolved salt stored in soils | kg |
| [`soilmn_kg`](soilmn_kg.md) | Mineral salt stored in soils | kg |
| [`aquds_kg`](aquds_kg.md) | Dissolved salt stored in aquifers | kg |
| [`aqumn_kg`](aqumn_kg.md) | Mineral salt stored in aquifers | kg |

## Routing-unit salt balance

The `rout_unit_salt_*` files report the eight ions for each of these exact heading groups:

| Field | Description | Unit |
| --- | --- | --- |
| [`total_so4`](total_so4.md) | Sulfate: total salt load from the routing unit | kg |
| [`total_ca`](total_ca.md) | Calcium: total salt load from the routing unit | kg |
| [`total_mg`](total_mg.md) | Magnesium: total salt load from the routing unit | kg |
| [`total_na`](total_na.md) | Sodium: total salt load from the routing unit | kg |
| [`total_k`](total_k.md) | Potassium: total salt load from the routing unit | kg |
| [`total_cl`](total_cl.md) | Chloride: total salt load from the routing unit | kg |
| [`total_co3`](total_co3.md) | Carbonate: total salt load from the routing unit | kg |
| [`total_hco3`](total_hco3.md) | Bicarbonate: total salt load from the routing unit | kg |
| [`perc_so4`](perc_so4.md) | Sulfate: percolation | kg |
| [`perc_ca`](perc_ca.md) | Calcium: percolation | kg |
| [`perc_mg`](perc_mg.md) | Magnesium: percolation | kg |
| [`perc_na`](perc_na.md) | Sodium: percolation | kg |
| [`perc_k`](perc_k.md) | Potassium: percolation | kg |
| [`perc_cl`](perc_cl.md) | Chloride: percolation | kg |
| [`perc_co3`](perc_co3.md) | Carbonate: percolation | kg |
| [`perc_hco3`](perc_hco3.md) | Bicarbonate: percolation | kg |
| [`surq_so4`](surq_so4.md) | Sulfate: surface runoff | kg |
| [`surq_ca`](surq_ca.md) | Calcium: surface runoff | kg |
| [`surq_mg`](surq_mg.md) | Magnesium: surface runoff | kg |
| [`surq_na`](surq_na.md) | Sodium: surface runoff | kg |
| [`surq_k`](surq_k.md) | Potassium: surface runoff | kg |
| [`surq_cl`](surq_cl.md) | Chloride: surface runoff | kg |
| [`surq_co3`](surq_co3.md) | Carbonate: surface runoff | kg |
| [`surq_hco3`](surq_hco3.md) | Bicarbonate: surface runoff | kg |
| [`latq_so4`](latq_so4.md) | Sulfate: lateral flow | kg |
| [`latq_ca`](latq_ca.md) | Calcium: lateral flow | kg |
| [`latq_mg`](latq_mg.md) | Magnesium: lateral flow | kg |
| [`latq_na`](latq_na.md) | Sodium: lateral flow | kg |
| [`latq_k`](latq_k.md) | Potassium: lateral flow | kg |
| [`latq_cl`](latq_cl.md) | Chloride: lateral flow | kg |
| [`latq_co3`](latq_co3.md) | Carbonate: lateral flow | kg |
| [`latq_hco3`](latq_hco3.md) | Bicarbonate: lateral flow | kg |
| [`tile_so4`](tile_so4.md) | Sulfate: tile flow | kg |
| [`tile_ca`](tile_ca.md) | Calcium: tile flow | kg |
| [`tile_mg`](tile_mg.md) | Magnesium: tile flow | kg |
| [`tile_na`](tile_na.md) | Sodium: tile flow | kg |
| [`tile_k`](tile_k.md) | Potassium: tile flow | kg |
| [`tile_cl`](tile_cl.md) | Chloride: tile flow | kg |
| [`tile_co3`](tile_co3.md) | Carbonate: tile flow | kg |
| [`tile_hco3`](tile_hco3.md) | Bicarbonate: tile flow | kg |
| [`wtsp_so4`](wtsp_so4.md) | Sulfate: wetland seepage | kg |
| [`wtsp_ca`](wtsp_ca.md) | Calcium: wetland seepage | kg |
| [`wtsp_mg`](wtsp_mg.md) | Magnesium: wetland seepage | kg |
| [`wtsp_na`](wtsp_na.md) | Sodium: wetland seepage | kg |
| [`wtsp_k`](wtsp_k.md) | Potassium: wetland seepage | kg |
| [`wtsp_cl`](wtsp_cl.md) | Chloride: wetland seepage | kg |
| [`wtsp_co3`](wtsp_co3.md) | Carbonate: wetland seepage | kg |
| [`wtsp_hco3`](wtsp_hco3.md) | Bicarbonate: wetland seepage | kg |
| [`irsw_so4`](irsw_so4.md) | Sulfate: surface-water irrigation | kg |
| [`irsw_ca`](irsw_ca.md) | Calcium: surface-water irrigation | kg |
| [`irsw_mg`](irsw_mg.md) | Magnesium: surface-water irrigation | kg |
| [`irsw_na`](irsw_na.md) | Sodium: surface-water irrigation | kg |
| [`irsw_k`](irsw_k.md) | Potassium: surface-water irrigation | kg |
| [`irsw_cl`](irsw_cl.md) | Chloride: surface-water irrigation | kg |
| [`irsw_co3`](irsw_co3.md) | Carbonate: surface-water irrigation | kg |
| [`irsw_hco3`](irsw_hco3.md) | Bicarbonate: surface-water irrigation | kg |
| [`irgw_so4`](irgw_so4.md) | Sulfate: groundwater irrigation | kg |
| [`irgw_ca`](irgw_ca.md) | Calcium: groundwater irrigation | kg |
| [`irgw_mg`](irgw_mg.md) | Magnesium: groundwater irrigation | kg |
| [`irgw_na`](irgw_na.md) | Sodium: groundwater irrigation | kg |
| [`irgw_k`](irgw_k.md) | Potassium: groundwater irrigation | kg |
| [`irgw_cl`](irgw_cl.md) | Chloride: groundwater irrigation | kg |
| [`irgw_co3`](irgw_co3.md) | Carbonate: groundwater irrigation | kg |
| [`irgw_hco3`](irgw_hco3.md) | Bicarbonate: groundwater irrigation | kg |
| [`irwo_so4`](irwo_so4.md) | Sulfate: outside-source irrigation | kg |
| [`irwo_ca`](irwo_ca.md) | Calcium: outside-source irrigation | kg |
| [`irwo_mg`](irwo_mg.md) | Magnesium: outside-source irrigation | kg |
| [`irwo_na`](irwo_na.md) | Sodium: outside-source irrigation | kg |
| [`irwo_k`](irwo_k.md) | Potassium: outside-source irrigation | kg |
| [`irwo_cl`](irwo_cl.md) | Chloride: outside-source irrigation | kg |
| [`irwo_co3`](irwo_co3.md) | Carbonate: outside-source irrigation | kg |
| [`irwo_hco3`](irwo_hco3.md) | Bicarbonate: outside-source irrigation | kg |
| [`rain_so4`](rain_so4.md) | Sulfate: rainfall input | kg |
| [`rain_ca`](rain_ca.md) | Calcium: rainfall input | kg |
| [`rain_mg`](rain_mg.md) | Magnesium: rainfall input | kg |
| [`rain_na`](rain_na.md) | Sodium: rainfall input | kg |
| [`rain_k`](rain_k.md) | Potassium: rainfall input | kg |
| [`rain_cl`](rain_cl.md) | Chloride: rainfall input | kg |
| [`rain_co3`](rain_co3.md) | Carbonate: rainfall input | kg |
| [`rain_hco3`](rain_hco3.md) | Bicarbonate: rainfall input | kg |
| [`dryd_so4`](dryd_so4.md) | Sulfate: dry deposition | kg |
| [`dryd_ca`](dryd_ca.md) | Calcium: dry deposition | kg |
| [`dryd_mg`](dryd_mg.md) | Magnesium: dry deposition | kg |
| [`dryd_na`](dryd_na.md) | Sodium: dry deposition | kg |
| [`dryd_k`](dryd_k.md) | Potassium: dry deposition | kg |
| [`dryd_cl`](dryd_cl.md) | Chloride: dry deposition | kg |
| [`dryd_co3`](dryd_co3.md) | Carbonate: dry deposition | kg |
| [`dryd_hco3`](dryd_hco3.md) | Bicarbonate: dry deposition | kg |
| [`road_so4`](road_so4.md) | Sulfate: road-salt application | kg |
| [`road_ca`](road_ca.md) | Calcium: road-salt application | kg |
| [`road_mg`](road_mg.md) | Magnesium: road-salt application | kg |
| [`road_na`](road_na.md) | Sodium: road-salt application | kg |
| [`road_k`](road_k.md) | Potassium: road-salt application | kg |
| [`road_cl`](road_cl.md) | Chloride: road-salt application | kg |
| [`road_co3`](road_co3.md) | Carbonate: road-salt application | kg |
| [`road_hco3`](road_hco3.md) | Bicarbonate: road-salt application | kg |
| [`fert_so4`](fert_so4.md) | Sulfate: fertilizer input | kg |
| [`fert_ca`](fert_ca.md) | Calcium: fertilizer input | kg |
| [`fert_mg`](fert_mg.md) | Magnesium: fertilizer input | kg |
| [`fert_na`](fert_na.md) | Sodium: fertilizer input | kg |
| [`fert_k`](fert_k.md) | Potassium: fertilizer input | kg |
| [`fert_cl`](fert_cl.md) | Chloride: fertilizer input | kg |
| [`fert_co3`](fert_co3.md) | Carbonate: fertilizer input | kg |
| [`fert_hco3`](fert_hco3.md) | Bicarbonate: fertilizer input | kg |
| [`amnd_so4`](amnd_so4.md) | Sulfate: amendment input | kg |
| [`amnd_ca`](amnd_ca.md) | Calcium: amendment input | kg |
| [`amnd_mg`](amnd_mg.md) | Magnesium: amendment input | kg |
| [`amnd_na`](amnd_na.md) | Sodium: amendment input | kg |
| [`amnd_k`](amnd_k.md) | Potassium: amendment input | kg |
| [`amnd_cl`](amnd_cl.md) | Chloride: amendment input | kg |
| [`amnd_co3`](amnd_co3.md) | Carbonate: amendment input | kg |
| [`amnd_hco3`](amnd_hco3.md) | Bicarbonate: amendment input | kg |
| [`uptk_so4`](uptk_so4.md) | Sulfate: plant uptake | kg |
| [`uptk_ca`](uptk_ca.md) | Calcium: plant uptake | kg |
| [`uptk_mg`](uptk_mg.md) | Magnesium: plant uptake | kg |
| [`uptk_na`](uptk_na.md) | Sodium: plant uptake | kg |
| [`uptk_k`](uptk_k.md) | Potassium: plant uptake | kg |
| [`uptk_cl`](uptk_cl.md) | Chloride: plant uptake | kg |
| [`uptk_co3`](uptk_co3.md) | Carbonate: plant uptake | kg |
| [`uptk_hco3`](uptk_hco3.md) | Bicarbonate: plant uptake | kg |
| [`dssl_total`](dssl_total-routing-unit-salt-balance.md) | Total mineral dissolution | kg |

HRU salt output has a different 159-heading schema and is documented on the [HRU Salt](../hru-salt/README.md) page.

## Channel salt

The `channel_salt_*` files use the common identifiers followed by these exact heading groups:

| Field | Description | Unit |
| --- | --- | --- |
| [`so4_in`](so4_in.md) | Sulfate entering the channel | kg |
| [`ca_in`](ca_in.md) | Calcium entering the channel | kg |
| [`mg_in`](mg_in.md) | Magnesium entering the channel | kg |
| [`na_in`](na_in.md) | Sodium entering the channel | kg |
| [`k_in`](k_in.md) | Potassium entering the channel | kg |
| [`cl_in`](cl_in.md) | Chloride entering the channel | kg |
| [`co3_in`](co3_in.md) | Carbonate entering the channel | kg |
| [`hco3_in`](hco3_in.md) | Bicarbonate entering the channel | kg |
| [`so4_gw`](so4_gw.md) | Sulfate entering the channel | kg |
| [`ca_gw`](ca_gw.md) | Calcium entering the channel | kg |
| [`mg_gw`](mg_gw.md) | Magnesium entering the channel | kg |
| [`na_gw`](na_gw.md) | Sodium entering the channel | kg |
| [`k_gw`](k_gw.md) | Potassium entering the channel | kg |
| [`cl_gw`](cl_gw.md) | Chloride entering the channel | kg |
| [`co3_gw`](co3_gw.md) | Carbonate entering the channel | kg |
| [`hco3_gw`](hco3_gw.md) | Bicarbonate entering the channel | kg |
| [`so4_out`](so4_out.md) | Sulfate leaving the channel | kg |
| [`ca_out`](ca_out.md) | Calcium leaving the channel | kg |
| [`mg_out`](mg_out.md) | Magnesium leaving the channel | kg |
| [`na_out`](na_out.md) | Sodium leaving the channel | kg |
| [`k_out`](k_out.md) | Potassium leaving the channel | kg |
| [`cl_out`](cl_out.md) | Chloride leaving the channel | kg |
| [`co3_out`](co3_out.md) | Carbonate leaving the channel | kg |
| [`hco3_out`](hco3_out.md) | Bicarbonate leaving the channel | kg |
| [`so4_seep`](so4_seep.md) | Sulfate lost through channel seepage | kg |
| [`ca_seep`](ca_seep.md) | Calcium lost through channel seepage | kg |
| [`mg_seep`](mg_seep.md) | Magnesium lost through channel seepage | kg |
| [`na_seep`](na_seep.md) | Sodium lost through channel seepage | kg |
| [`k_seep`](k_seep.md) | Potassium lost through channel seepage | kg |
| [`cl_seep`](cl_seep.md) | Chloride lost through channel seepage | kg |
| [`co3_seep`](co3_seep.md) | Carbonate lost through channel seepage | kg |
| [`hco3_seep`](hco3_seep.md) | Bicarbonate lost through channel seepage | kg |
| [`so4_irr`](so4_irr.md) | Sulfate removed for irrigation | kg |
| [`ca_irr`](ca_irr.md) | Calcium removed for irrigation | kg |
| [`mg_irr`](mg_irr.md) | Magnesium removed for irrigation | kg |
| [`na_irr`](na_irr.md) | Sodium removed for irrigation | kg |
| [`k_irr`](k_irr.md) | Potassium removed for irrigation | kg |
| [`cl_irr`](cl_irr.md) | Chloride removed for irrigation | kg |
| [`co3_irr`](co3_irr.md) | Carbonate removed for irrigation | kg |
| [`hco3_irr`](hco3_irr.md) | Bicarbonate removed for irrigation | kg |
| [`so4_div`](so4_div.md) | Sulfate removed by diversion | kg |
| [`ca_div`](ca_div.md) | Calcium removed by diversion | kg |
| [`mg_div`](mg_div.md) | Magnesium removed by diversion | kg |
| [`na_div`](na_div.md) | Sodium removed by diversion | kg |
| [`k_div`](k_div.md) | Potassium removed by diversion | kg |
| [`cl_div`](cl_div.md) | Chloride removed by diversion | kg |
| [`co3_div`](co3_div.md) | Carbonate removed by diversion | kg |
| [`hco3_div`](hco3_div.md) | Bicarbonate removed by diversion | kg |
| [`so4_mass`](so4_mass.md) | Sulfate stored in channel water | kg |
| [`ca_mass`](ca_mass.md) | Calcium stored in channel water | kg |
| [`mg_mass`](mg_mass.md) | Magnesium stored in channel water | kg |
| [`na_mass`](na_mass.md) | Sodium stored in channel water | kg |
| [`k_mass`](k_mass.md) | Potassium stored in channel water | kg |
| [`cl_mass`](cl_mass.md) | Chloride stored in channel water | kg |
| [`co3_mass`](co3_mass.md) | Carbonate stored in channel water | kg |
| [`hco3_mass`](hco3_mass.md) | Bicarbonate stored in channel water | kg |
| [`so4_conc`](so4_conc.md) | Sulfate concentration in channel water | g/m3 |
| [`ca_conc`](ca_conc.md) | Calcium concentration in channel water | g/m3 |
| [`mg_conc`](mg_conc.md) | Magnesium concentration in channel water | g/m3 |
| [`na_conc`](na_conc.md) | Sodium concentration in channel water | g/m3 |
| [`k_conc`](k_conc.md) | Potassium concentration in channel water | g/m3 |
| [`cl_conc`](cl_conc.md) | Chloride concentration in channel water | g/m3 |
| [`co3_conc`](co3_conc.md) | Carbonate concentration in channel water | g/m3 |
| [`hco3_conc`](hco3_conc.md) | Bicarbonate concentration in channel water | g/m3 |

## Aquifer salt

The `aquifer_salt_*` files use these exact heading groups:

| Field | Description | Unit |
| --- | --- | --- |
| [`gw_so4`](gw_so4.md) | Sulfate stored in groundwater | kg |
| [`gw_ca`](gw_ca.md) | Calcium stored in groundwater | kg |
| [`gw_mg`](gw_mg.md) | Magnesium stored in groundwater | kg |
| [`gw_na`](gw_na.md) | Sodium stored in groundwater | kg |
| [`gw_k`](gw_k.md) | Potassium stored in groundwater | kg |
| [`gw_cl`](gw_cl.md) | Chloride stored in groundwater | kg |
| [`gw_co3`](gw_co3.md) | Carbonate stored in groundwater | kg |
| [`gw_hco3`](gw_hco3.md) | Bicarbonate stored in groundwater | kg |
| [`rchg_so4`](rchg_so4.md) | Sulfate entering with recharge | kg |
| [`rchg_ca`](rchg_ca.md) | Calcium entering with recharge | kg |
| [`rchg_mg`](rchg_mg.md) | Magnesium entering with recharge | kg |
| [`rchg_na`](rchg_na.md) | Sodium entering with recharge | kg |
| [`rchg_k`](rchg_k.md) | Potassium entering with recharge | kg |
| [`rchg_cl`](rchg_cl.md) | Chloride entering with recharge | kg |
| [`rchg_co3`](rchg_co3.md) | Carbonate entering with recharge | kg |
| [`rchg_hco3`](rchg_hco3.md) | Bicarbonate entering with recharge | kg |
| [`seep_so4`](seep_so4.md) | Sulfate leaving through aquifer seepage | kg |
| [`seep_ca`](seep_ca.md) | Calcium leaving through aquifer seepage | kg |
| [`seep_mg`](seep_mg.md) | Magnesium leaving through aquifer seepage | kg |
| [`seep_na`](seep_na.md) | Sodium leaving through aquifer seepage | kg |
| [`seep_k`](seep_k.md) | Potassium leaving through aquifer seepage | kg |
| [`seep_cl`](seep_cl.md) | Chloride leaving through aquifer seepage | kg |
| [`seep_co3`](seep_co3.md) | Carbonate leaving through aquifer seepage | kg |
| [`seep_hco3`](seep_hco3.md) | Bicarbonate leaving through aquifer seepage | kg |
| [`irr_so4`](irr_so4.md) | Sulfate removed for irrigation | kg |
| [`irr_ca`](irr_ca.md) | Calcium removed for irrigation | kg |
| [`irr_mg`](irr_mg.md) | Magnesium removed for irrigation | kg |
| [`irr_na`](irr_na.md) | Sodium removed for irrigation | kg |
| [`irr_k`](irr_k.md) | Potassium removed for irrigation | kg |
| [`irr_cl`](irr_cl.md) | Chloride removed for irrigation | kg |
| [`irr_co3`](irr_co3.md) | Carbonate removed for irrigation | kg |
| [`irr_hco3`](irr_hco3.md) | Bicarbonate removed for irrigation | kg |
| [`div_so4`](div_so4.md) | Sulfate removed by diversion | kg |
| [`div_ca`](div_ca.md) | Calcium removed by diversion | kg |
| [`div_mg`](div_mg.md) | Magnesium removed by diversion | kg |
| [`div_na`](div_na.md) | Sodium removed by diversion | kg |
| [`div_k`](div_k.md) | Potassium removed by diversion | kg |
| [`div_cl`](div_cl.md) | Chloride removed by diversion | kg |
| [`div_co3`](div_co3.md) | Carbonate removed by diversion | kg |
| [`div_hco3`](div_hco3.md) | Bicarbonate removed by diversion | kg |
| [`mass_so4`](mass_so4.md) | Sulfate: aquifer salt mass | kg |
| [`mass_ca`](mass_ca.md) | Calcium: aquifer salt mass | kg |
| [`mass_mg`](mass_mg.md) | Magnesium: aquifer salt mass | kg |
| [`mass_na`](mass_na.md) | Sodium: aquifer salt mass | kg |
| [`mass_k`](mass_k.md) | Potassium: aquifer salt mass | kg |
| [`mass_cl`](mass_cl.md) | Chloride: aquifer salt mass | kg |
| [`mass_co3`](mass_co3.md) | Carbonate: aquifer salt mass | kg |
| [`mass_hco3`](mass_hco3.md) | Bicarbonate: aquifer salt mass | kg |
| [`conc_so4`](conc_so4.md) | Sulfate: groundwater concentration | g/m3 |
| [`conc_ca`](conc_ca.md) | Calcium: groundwater concentration | g/m3 |
| [`conc_mg`](conc_mg.md) | Magnesium: groundwater concentration | g/m3 |
| [`conc_na`](conc_na.md) | Sodium: groundwater concentration | g/m3 |
| [`conc_k`](conc_k.md) | Potassium: groundwater concentration | g/m3 |
| [`conc_cl`](conc_cl.md) | Chloride: groundwater concentration | g/m3 |
| [`conc_co3`](conc_co3.md) | Carbonate: groundwater concentration | g/m3 |
| [`conc_hco3`](conc_hco3.md) | Bicarbonate: groundwater concentration | g/m3 |
| [`dssl_total`](dssl_total-aquifer-salt.md) | Salt dissolved from aquifer minerals | kg |

Average-annual mass fluxes are reported per year; concentration remains a state value.

## Reservoir and wetland salt

The `reservoir_salt_*` and `wetland_salt_*` files share one schema. Their exact eight-ion groups are:

- `so4_in`, `ca_in`, `mg_in`, `na_in`, `k_in`, `cl_in`, `co3_in`, `hco3_in`.
- `so4_out`, `ca_out`, `mg_out`, `na_out`, `k_out`, `cl_out`, `co3_out`, `hco3_out`.
- `so4_seep`, `ca_seep`, `mg_seep`, `na_seep`, `k_seep`, `cl_seep`, `co3_seep`, `hco3_seep`.
- `so4_fert`, `ca_fert`, `mg_fert`, `na_fert`, `k_fert`, `cl_fert`, `co3_fert`, `hco3_fert`.
- `so4_irrg`, `ca_irrg`, `mg_irrg`, `na_irrg`, `k_irrg`, `cl_irrg`, `co3_irrg`, `hco3_irrg`.
- `so4_div`, `ca_div`, `mg_div`, `na_div`, `k_div`, `cl_div`, `co3_div`, `hco3_div`.
- `so4_mass`, `ca_mass`, `mg_mass`, `na_mass`, `k_mass`, `cl_mass`, `co3_mass`, `hco3_mass`.
- `so4_conc`, `ca_conc`, `mg_conc`, `na_conc`, `k_conc`, `cl_conc`, `co3_conc`, `hco3_conc`.

The last heading is `vol_m3`.

Mass and flux headings are kg, concentration headings are g/m3, and `vol_m3` is water volume in m3.
