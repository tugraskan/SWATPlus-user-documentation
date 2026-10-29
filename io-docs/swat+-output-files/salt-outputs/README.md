# Salt Outputs

SWAT+ can report salt balances for the basin, routing units, HRUs, channels, aquifers, reservoirs, and wetlands. These files are produced only when the salt module is configured and the corresponding print option is enabled. Daily, monthly, yearly, and average-annual files use the suffixes `_day`, `_mon`, `_yr`, and `_aa`; TXT and CSV variants share the same data headings.

The salt ions always appear in this order: sulfate (`so4`), calcium (`ca`), magnesium (`mg`), sodium (`na`), potassium (`k`), chloride (`cl`), carbonate (`co3`), and bicarbonate (`hco3`). Every name in the Field column below is an exact printed heading.

Unless a section states otherwise, daily, monthly, and yearly mass fields are printed in kg for the reporting interval. In average-annual files, the printed units row labels flux fields as kg/yr. Stored mass remains a state value, although some average-annual preambles also print kg/yr for those headings; the tables below reproduce the source-defined output rather than reinterpreting it. Concentrations are printed in g/m3.

The common identifying headings are `jday`, `mon`, `day`, `yr`, `unit`, and `gis_id`. Basin salt output instead begins with `yr`, `mo`, and `jday`.

## Basin salt balance

The files are `basin_salt_day`, `basin_salt_mon`, `basin_salt_yr`, and `basin_salt_aa` with `.txt` and `.csv` variants. Each mass-balance heading represents the total of all eight ions.

| Field | Description | Unit |
| --- | --- | --- |
| [`lat_kg`](lat_kg.md), [`gw_kg`](gw_kg.md), [`sur_kg`](sur_kg.md), [`urb_kg`](urb_kg.md), [`wet_kg`](wet_kg.md), [`tile_kg`](tile_kg.md) | Salt reaching streams through lateral flow, groundwater, surface runoff, urban runoff, wetlands, and tile drainage | kg |
| [`perc_kg`](perc_kg.md), [`gwup_kg`](gwup_kg.md), [`wtsp_kg`](wtsp_kg.md) | Soil-aquifer and wetland-soil salt transfers | kg |
| [`irsw_kg`](irsw_kg.md), [`irgw_kg`](irgw_kg.md), [`irwo_kg`](irwo_kg.md) | Salt added by surface-water, groundwater, and outside-source irrigation | kg |
| [`rain_kg`](rain_kg.md), [`dryd_kg`](dryd_kg.md), [`road_kg`](road_kg.md), [`fert_kg`](fert_kg.md), [`amnd_kg`](amnd_kg.md) | Salt inputs from rain, dry deposition, road salt, fertilizer, and amendments | kg |
| [`uptk_kg`](uptk_kg.md) | Salt removed by plant uptake | kg |
| [`ptso_kg`](ptso_kg.md), [`ptout_kg`](ptout_kg.md) | Point-source salt entering and leaving the basin | kg |
| [`rchg_kg`](rchg_kg.md), [`seep_kg`](seep_kg.md) | Aquifer recharge and seepage salt transfers | kg |
| [`dssl_kg`](dssl_kg.md), [`dsaq_kg`](dsaq_kg.md) | Mineral dissolution in soils and aquifers | kg |
| [`soilds_kg`](soilds_kg.md), [`soilmn_kg`](soilmn_kg.md), [`aquds_kg`](aquds_kg.md), [`aqumn_kg`](aqumn_kg.md) | Dissolved and mineral salt storage in soils and aquifers | kg |

## Routing-unit salt balance

The `rout_unit_salt_*` files report the eight ions for each of these exact heading groups:

| Field | Description | Unit |
| --- | --- | --- |
| [`total_so4`](total_so4.md), [`total_ca`](total_ca.md), [`total_mg`](total_mg.md), [`total_na`](total_na.md), [`total_k`](total_k.md), [`total_cl`](total_cl.md), [`total_co3`](total_co3.md), [`total_hco3`](total_hco3.md) | Total salt load from the routing unit | kg |
| [`perc_so4`](perc_so4.md), [`perc_ca`](perc_ca.md), [`perc_mg`](perc_mg.md), [`perc_na`](perc_na.md), [`perc_k`](perc_k.md), [`perc_cl`](perc_cl.md), [`perc_co3`](perc_co3.md), [`perc_hco3`](perc_hco3.md) | Percolation | kg |
| [`surq_so4`](surq_so4.md), [`surq_ca`](surq_ca.md), [`surq_mg`](surq_mg.md), [`surq_na`](surq_na.md), [`surq_k`](surq_k.md), [`surq_cl`](surq_cl.md), [`surq_co3`](surq_co3.md), [`surq_hco3`](surq_hco3.md) | Surface runoff | kg |
| [`latq_so4`](latq_so4.md), [`latq_ca`](latq_ca.md), [`latq_mg`](latq_mg.md), [`latq_na`](latq_na.md), [`latq_k`](latq_k.md), [`latq_cl`](latq_cl.md), [`latq_co3`](latq_co3.md), [`latq_hco3`](latq_hco3.md) | Lateral flow | kg |
| [`tile_so4`](tile_so4.md), [`tile_ca`](tile_ca.md), [`tile_mg`](tile_mg.md), [`tile_na`](tile_na.md), [`tile_k`](tile_k.md), [`tile_cl`](tile_cl.md), [`tile_co3`](tile_co3.md), [`tile_hco3`](tile_hco3.md) | Tile flow | kg |
| [`wtsp_so4`](wtsp_so4.md), [`wtsp_ca`](wtsp_ca.md), [`wtsp_mg`](wtsp_mg.md), [`wtsp_na`](wtsp_na.md), [`wtsp_k`](wtsp_k.md), [`wtsp_cl`](wtsp_cl.md), [`wtsp_co3`](wtsp_co3.md), [`wtsp_hco3`](wtsp_hco3.md) | Wetland seepage | kg |
| [`irsw_so4`](irsw_so4.md), [`irsw_ca`](irsw_ca.md), [`irsw_mg`](irsw_mg.md), [`irsw_na`](irsw_na.md), [`irsw_k`](irsw_k.md), [`irsw_cl`](irsw_cl.md), [`irsw_co3`](irsw_co3.md), [`irsw_hco3`](irsw_hco3.md) | Surface-water irrigation | kg |
| [`irgw_so4`](irgw_so4.md), [`irgw_ca`](irgw_ca.md), [`irgw_mg`](irgw_mg.md), [`irgw_na`](irgw_na.md), [`irgw_k`](irgw_k.md), [`irgw_cl`](irgw_cl.md), [`irgw_co3`](irgw_co3.md), [`irgw_hco3`](irgw_hco3.md) | Groundwater irrigation | kg |
| [`irwo_so4`](irwo_so4.md), [`irwo_ca`](irwo_ca.md), [`irwo_mg`](irwo_mg.md), [`irwo_na`](irwo_na.md), [`irwo_k`](irwo_k.md), [`irwo_cl`](irwo_cl.md), [`irwo_co3`](irwo_co3.md), [`irwo_hco3`](irwo_hco3.md) | Outside-source irrigation | kg |
| [`rain_so4`](rain_so4.md), [`rain_ca`](rain_ca.md), [`rain_mg`](rain_mg.md), [`rain_na`](rain_na.md), [`rain_k`](rain_k.md), [`rain_cl`](rain_cl.md), [`rain_co3`](rain_co3.md), [`rain_hco3`](rain_hco3.md) | Rainfall input | kg |
| [`dryd_so4`](dryd_so4.md), [`dryd_ca`](dryd_ca.md), [`dryd_mg`](dryd_mg.md), [`dryd_na`](dryd_na.md), [`dryd_k`](dryd_k.md), [`dryd_cl`](dryd_cl.md), [`dryd_co3`](dryd_co3.md), [`dryd_hco3`](dryd_hco3.md) | Dry deposition | kg |
| [`road_so4`](road_so4.md), [`road_ca`](road_ca.md), [`road_mg`](road_mg.md), [`road_na`](road_na.md), [`road_k`](road_k.md), [`road_cl`](road_cl.md), [`road_co3`](road_co3.md), [`road_hco3`](road_hco3.md) | Road-salt application | kg |
| [`fert_so4`](fert_so4.md), [`fert_ca`](fert_ca.md), [`fert_mg`](fert_mg.md), [`fert_na`](fert_na.md), [`fert_k`](fert_k.md), [`fert_cl`](fert_cl.md), [`fert_co3`](fert_co3.md), [`fert_hco3`](fert_hco3.md) | Fertilizer input | kg |
| [`amnd_so4`](amnd_so4.md), [`amnd_ca`](amnd_ca.md), [`amnd_mg`](amnd_mg.md), [`amnd_na`](amnd_na.md), [`amnd_k`](amnd_k.md), [`amnd_cl`](amnd_cl.md), [`amnd_co3`](amnd_co3.md), [`amnd_hco3`](amnd_hco3.md) | Amendment input | kg |
| [`uptk_so4`](uptk_so4.md), [`uptk_ca`](uptk_ca.md), [`uptk_mg`](uptk_mg.md), [`uptk_na`](uptk_na.md), [`uptk_k`](uptk_k.md), [`uptk_cl`](uptk_cl.md), [`uptk_co3`](uptk_co3.md), [`uptk_hco3`](uptk_hco3.md) | Plant uptake | kg |
| [`dssl_total`](dssl_total-routing-unit-salt-balance.md) | Total mineral dissolution | kg |

HRU salt output has a different 159-heading schema and is documented on the [HRU Salt](../hru-salt/README.md) page.

## Channel salt

The `channel_salt_*` files use the common identifiers followed by these exact heading groups:

| Field | Description | Unit |
| --- | --- | --- |
| [`so4_in`](so4_in.md), [`ca_in`](ca_in.md), [`mg_in`](mg_in.md), [`na_in`](na_in.md), [`k_in`](k_in.md), [`cl_in`](cl_in.md), [`co3_in`](co3_in.md), [`hco3_in`](hco3_in.md) | Salt entering the channel | kg |
| [`so4_gw`](so4_gw.md), [`ca_gw`](ca_gw.md), [`mg_gw`](mg_gw.md), [`na_gw`](na_gw.md), [`k_gw`](k_gw.md), [`cl_gw`](cl_gw.md), [`co3_gw`](co3_gw.md), [`hco3_gw`](hco3_gw.md) | Groundwater salt entering the channel | kg |
| [`so4_out`](so4_out.md), [`ca_out`](ca_out.md), [`mg_out`](mg_out.md), [`na_out`](na_out.md), [`k_out`](k_out.md), [`cl_out`](cl_out.md), [`co3_out`](co3_out.md), [`hco3_out`](hco3_out.md) | Salt leaving the channel | kg |
| [`so4_seep`](so4_seep.md), [`ca_seep`](ca_seep.md), [`mg_seep`](mg_seep.md), [`na_seep`](na_seep.md), [`k_seep`](k_seep.md), [`cl_seep`](cl_seep.md), [`co3_seep`](co3_seep.md), [`hco3_seep`](hco3_seep.md) | Salt lost through channel seepage | kg |
| [`so4_irr`](so4_irr.md), [`ca_irr`](ca_irr.md), [`mg_irr`](mg_irr.md), [`na_irr`](na_irr.md), [`k_irr`](k_irr.md), [`cl_irr`](cl_irr.md), [`co3_irr`](co3_irr.md), [`hco3_irr`](hco3_irr.md) | Salt removed for irrigation | kg |
| [`so4_div`](so4_div.md), [`ca_div`](ca_div.md), [`mg_div`](mg_div.md), [`na_div`](na_div.md), [`k_div`](k_div.md), [`cl_div`](cl_div.md), [`co3_div`](co3_div.md), [`hco3_div`](hco3_div.md) | Salt removed by diversion | kg |
| [`so4_mass`](so4_mass.md), [`ca_mass`](ca_mass.md), [`mg_mass`](mg_mass.md), [`na_mass`](na_mass.md), [`k_mass`](k_mass.md), [`cl_mass`](cl_mass.md), [`co3_mass`](co3_mass.md), [`hco3_mass`](hco3_mass.md) | Salt stored in channel water | kg |
| [`so4_conc`](so4_conc.md), [`ca_conc`](ca_conc.md), [`mg_conc`](mg_conc.md), [`na_conc`](na_conc.md), [`k_conc`](k_conc.md), [`cl_conc`](cl_conc.md), [`co3_conc`](co3_conc.md), [`hco3_conc`](hco3_conc.md) | Salt concentration in channel water | g/m3 |

## Aquifer salt

The `aquifer_salt_*` files use these exact heading groups:

| Field | Description | Unit |
| --- | --- | --- |
| [`gw_so4`](gw_so4.md), [`gw_ca`](gw_ca.md), [`gw_mg`](gw_mg.md), [`gw_na`](gw_na.md), [`gw_k`](gw_k.md), [`gw_cl`](gw_cl.md), [`gw_co3`](gw_co3.md), [`gw_hco3`](gw_hco3.md) | Salt stored in groundwater | kg |
| [`rchg_so4`](rchg_so4.md), [`rchg_ca`](rchg_ca.md), [`rchg_mg`](rchg_mg.md), [`rchg_na`](rchg_na.md), [`rchg_k`](rchg_k.md), [`rchg_cl`](rchg_cl.md), [`rchg_co3`](rchg_co3.md), [`rchg_hco3`](rchg_hco3.md) | Salt entering with recharge | kg |
| [`seep_so4`](seep_so4.md), [`seep_ca`](seep_ca.md), [`seep_mg`](seep_mg.md), [`seep_na`](seep_na.md), [`seep_k`](seep_k.md), [`seep_cl`](seep_cl.md), [`seep_co3`](seep_co3.md), [`seep_hco3`](seep_hco3.md) | Salt leaving through aquifer seepage | kg |
| [`irr_so4`](irr_so4.md), [`irr_ca`](irr_ca.md), [`irr_mg`](irr_mg.md), [`irr_na`](irr_na.md), [`irr_k`](irr_k.md), [`irr_cl`](irr_cl.md), [`irr_co3`](irr_co3.md), [`irr_hco3`](irr_hco3.md) | Salt removed for irrigation | kg |
| [`div_so4`](div_so4.md), [`div_ca`](div_ca.md), [`div_mg`](div_mg.md), [`div_na`](div_na.md), [`div_k`](div_k.md), [`div_cl`](div_cl.md), [`div_co3`](div_co3.md), [`div_hco3`](div_hco3.md) | Salt removed by diversion | kg |
| [`mass_so4`](mass_so4.md), [`mass_ca`](mass_ca.md), [`mass_mg`](mass_mg.md), [`mass_na`](mass_na.md), [`mass_k`](mass_k.md), [`mass_cl`](mass_cl.md), [`mass_co3`](mass_co3.md), [`mass_hco3`](mass_hco3.md) | Aquifer salt mass | kg |
| [`conc_so4`](conc_so4.md), [`conc_ca`](conc_ca.md), [`conc_mg`](conc_mg.md), [`conc_na`](conc_na.md), [`conc_k`](conc_k.md), [`conc_cl`](conc_cl.md), [`conc_co3`](conc_co3.md), [`conc_hco3`](conc_hco3.md) | Groundwater concentration | g/m3 |
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
