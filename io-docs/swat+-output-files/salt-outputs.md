# Salt Outputs

SWAT+ can report salt balances for the basin, routing units, HRUs, channels, aquifers, reservoirs, and wetlands. These files are produced only when the salt module is configured and the corresponding print option is enabled. Daily, monthly, yearly, and average-annual files use the suffixes `_day`, `_mon`, `_yr`, and `_aa`; TXT and CSV variants share the same data headings.

The salt ions always appear in this order: sulfate (`so4`), calcium (`ca`), magnesium (`mg`), sodium (`na`), potassium (`k`), chloride (`cl`), carbonate (`co3`), and bicarbonate (`hco3`). Every name in the Field column below is an exact printed heading.

Unless a section states otherwise, daily, monthly, and yearly mass fields are printed in kg for the reporting interval. In average-annual files, the printed units row labels flux fields as kg/yr. Stored mass remains a state value, although some average-annual preambles also print kg/yr for those headings; the tables below reproduce the source-defined output rather than reinterpreting it. Concentrations are printed in g/m3.

The common identifying headings are `jday`, `mon`, `day`, `yr`, `unit`, and `gis_id`. Basin salt output instead begins with `yr`, `mo`, and `jday`.

## Basin salt balance

The files are `basin_salt_day`, `basin_salt_mon`, `basin_salt_yr`, and `basin_salt_aa` with `.txt` and `.csv` variants. Each mass-balance heading represents the total of all eight ions.

| Field | Description | Unit |
| --- | --- | --- |
| [`lat_kg`](salt-outputs/lat_kg.md), [`gw_kg`](salt-outputs/gw_kg.md), [`sur_kg`](salt-outputs/sur_kg.md), [`urb_kg`](salt-outputs/urb_kg.md), [`wet_kg`](salt-outputs/wet_kg.md), [`tile_kg`](salt-outputs/tile_kg.md) | Salt reaching streams through lateral flow, groundwater, surface runoff, urban runoff, wetlands, and tile drainage | kg |
| [`perc_kg`](salt-outputs/perc_kg.md), [`gwup_kg`](salt-outputs/gwup_kg.md), [`wtsp_kg`](salt-outputs/wtsp_kg.md) | Soil-aquifer and wetland-soil salt transfers | kg |
| [`irsw_kg`](salt-outputs/irsw_kg.md), [`irgw_kg`](salt-outputs/irgw_kg.md), [`irwo_kg`](salt-outputs/irwo_kg.md) | Salt added by surface-water, groundwater, and outside-source irrigation | kg |
| [`rain_kg`](salt-outputs/rain_kg.md), [`dryd_kg`](salt-outputs/dryd_kg.md), [`road_kg`](salt-outputs/road_kg.md), [`fert_kg`](salt-outputs/fert_kg.md), [`amnd_kg`](salt-outputs/amnd_kg.md) | Salt inputs from rain, dry deposition, road salt, fertilizer, and amendments | kg |
| [`uptk_kg`](salt-outputs/uptk_kg.md) | Salt removed by plant uptake | kg |
| [`ptso_kg`](salt-outputs/ptso_kg.md), [`ptout_kg`](salt-outputs/ptout_kg.md) | Point-source salt entering and leaving the basin | kg |
| [`rchg_kg`](salt-outputs/rchg_kg.md), [`seep_kg`](salt-outputs/seep_kg.md) | Aquifer recharge and seepage salt transfers | kg |
| [`dssl_kg`](salt-outputs/dssl_kg.md), [`dsaq_kg`](salt-outputs/dsaq_kg.md) | Mineral dissolution in soils and aquifers | kg |
| [`soilds_kg`](salt-outputs/soilds_kg.md), [`soilmn_kg`](salt-outputs/soilmn_kg.md), [`aquds_kg`](salt-outputs/aquds_kg.md), [`aqumn_kg`](salt-outputs/aqumn_kg.md) | Dissolved and mineral salt storage in soils and aquifers | kg |

## Routing-unit salt balance

The `rout_unit_salt_*` files report the eight ions for each of these exact heading groups:

| Field | Description | Unit |
| --- | --- | --- |
| [`total_so4`](salt-outputs/total_so4.md), [`total_ca`](salt-outputs/total_ca.md), [`total_mg`](salt-outputs/total_mg.md), [`total_na`](salt-outputs/total_na.md), [`total_k`](salt-outputs/total_k.md), [`total_cl`](salt-outputs/total_cl.md), [`total_co3`](salt-outputs/total_co3.md), [`total_hco3`](salt-outputs/total_hco3.md) | Total salt load from the routing unit | kg |
| [`perc_so4`](salt-outputs/perc_so4.md), [`perc_ca`](salt-outputs/perc_ca.md), [`perc_mg`](salt-outputs/perc_mg.md), [`perc_na`](salt-outputs/perc_na.md), [`perc_k`](salt-outputs/perc_k.md), [`perc_cl`](salt-outputs/perc_cl.md), [`perc_co3`](salt-outputs/perc_co3.md), [`perc_hco3`](salt-outputs/perc_hco3.md) | Percolation | kg |
| [`surq_so4`](salt-outputs/surq_so4.md), [`surq_ca`](salt-outputs/surq_ca.md), [`surq_mg`](salt-outputs/surq_mg.md), [`surq_na`](salt-outputs/surq_na.md), [`surq_k`](salt-outputs/surq_k.md), [`surq_cl`](salt-outputs/surq_cl.md), [`surq_co3`](salt-outputs/surq_co3.md), [`surq_hco3`](salt-outputs/surq_hco3.md) | Surface runoff | kg |
| [`latq_so4`](salt-outputs/latq_so4.md), [`latq_ca`](salt-outputs/latq_ca.md), [`latq_mg`](salt-outputs/latq_mg.md), [`latq_na`](salt-outputs/latq_na.md), [`latq_k`](salt-outputs/latq_k.md), [`latq_cl`](salt-outputs/latq_cl.md), [`latq_co3`](salt-outputs/latq_co3.md), [`latq_hco3`](salt-outputs/latq_hco3.md) | Lateral flow | kg |
| [`tile_so4`](salt-outputs/tile_so4.md), [`tile_ca`](salt-outputs/tile_ca.md), [`tile_mg`](salt-outputs/tile_mg.md), [`tile_na`](salt-outputs/tile_na.md), [`tile_k`](salt-outputs/tile_k.md), [`tile_cl`](salt-outputs/tile_cl.md), [`tile_co3`](salt-outputs/tile_co3.md), [`tile_hco3`](salt-outputs/tile_hco3.md) | Tile flow | kg |
| [`wtsp_so4`](salt-outputs/wtsp_so4.md), [`wtsp_ca`](salt-outputs/wtsp_ca.md), [`wtsp_mg`](salt-outputs/wtsp_mg.md), [`wtsp_na`](salt-outputs/wtsp_na.md), [`wtsp_k`](salt-outputs/wtsp_k.md), [`wtsp_cl`](salt-outputs/wtsp_cl.md), [`wtsp_co3`](salt-outputs/wtsp_co3.md), [`wtsp_hco3`](salt-outputs/wtsp_hco3.md) | Wetland seepage | kg |
| [`irsw_so4`](salt-outputs/irsw_so4.md), [`irsw_ca`](salt-outputs/irsw_ca.md), [`irsw_mg`](salt-outputs/irsw_mg.md), [`irsw_na`](salt-outputs/irsw_na.md), [`irsw_k`](salt-outputs/irsw_k.md), [`irsw_cl`](salt-outputs/irsw_cl.md), [`irsw_co3`](salt-outputs/irsw_co3.md), [`irsw_hco3`](salt-outputs/irsw_hco3.md) | Surface-water irrigation | kg |
| [`irgw_so4`](salt-outputs/irgw_so4.md), [`irgw_ca`](salt-outputs/irgw_ca.md), [`irgw_mg`](salt-outputs/irgw_mg.md), [`irgw_na`](salt-outputs/irgw_na.md), [`irgw_k`](salt-outputs/irgw_k.md), [`irgw_cl`](salt-outputs/irgw_cl.md), [`irgw_co3`](salt-outputs/irgw_co3.md), [`irgw_hco3`](salt-outputs/irgw_hco3.md) | Groundwater irrigation | kg |
| [`irwo_so4`](salt-outputs/irwo_so4.md), [`irwo_ca`](salt-outputs/irwo_ca.md), [`irwo_mg`](salt-outputs/irwo_mg.md), [`irwo_na`](salt-outputs/irwo_na.md), [`irwo_k`](salt-outputs/irwo_k.md), [`irwo_cl`](salt-outputs/irwo_cl.md), [`irwo_co3`](salt-outputs/irwo_co3.md), [`irwo_hco3`](salt-outputs/irwo_hco3.md) | Outside-source irrigation | kg |
| [`rain_so4`](salt-outputs/rain_so4.md), [`rain_ca`](salt-outputs/rain_ca.md), [`rain_mg`](salt-outputs/rain_mg.md), [`rain_na`](salt-outputs/rain_na.md), [`rain_k`](salt-outputs/rain_k.md), [`rain_cl`](salt-outputs/rain_cl.md), [`rain_co3`](salt-outputs/rain_co3.md), [`rain_hco3`](salt-outputs/rain_hco3.md) | Rainfall input | kg |
| [`dryd_so4`](salt-outputs/dryd_so4.md), [`dryd_ca`](salt-outputs/dryd_ca.md), [`dryd_mg`](salt-outputs/dryd_mg.md), [`dryd_na`](salt-outputs/dryd_na.md), [`dryd_k`](salt-outputs/dryd_k.md), [`dryd_cl`](salt-outputs/dryd_cl.md), [`dryd_co3`](salt-outputs/dryd_co3.md), [`dryd_hco3`](salt-outputs/dryd_hco3.md) | Dry deposition | kg |
| [`road_so4`](salt-outputs/road_so4.md), [`road_ca`](salt-outputs/road_ca.md), [`road_mg`](salt-outputs/road_mg.md), [`road_na`](salt-outputs/road_na.md), [`road_k`](salt-outputs/road_k.md), [`road_cl`](salt-outputs/road_cl.md), [`road_co3`](salt-outputs/road_co3.md), [`road_hco3`](salt-outputs/road_hco3.md) | Road-salt application | kg |
| [`fert_so4`](salt-outputs/fert_so4.md), [`fert_ca`](salt-outputs/fert_ca.md), [`fert_mg`](salt-outputs/fert_mg.md), [`fert_na`](salt-outputs/fert_na.md), [`fert_k`](salt-outputs/fert_k.md), [`fert_cl`](salt-outputs/fert_cl.md), [`fert_co3`](salt-outputs/fert_co3.md), [`fert_hco3`](salt-outputs/fert_hco3.md) | Fertilizer input | kg |
| [`amnd_so4`](salt-outputs/amnd_so4.md), [`amnd_ca`](salt-outputs/amnd_ca.md), [`amnd_mg`](salt-outputs/amnd_mg.md), [`amnd_na`](salt-outputs/amnd_na.md), [`amnd_k`](salt-outputs/amnd_k.md), [`amnd_cl`](salt-outputs/amnd_cl.md), [`amnd_co3`](salt-outputs/amnd_co3.md), [`amnd_hco3`](salt-outputs/amnd_hco3.md) | Amendment input | kg |
| [`uptk_so4`](salt-outputs/uptk_so4.md), [`uptk_ca`](salt-outputs/uptk_ca.md), [`uptk_mg`](salt-outputs/uptk_mg.md), [`uptk_na`](salt-outputs/uptk_na.md), [`uptk_k`](salt-outputs/uptk_k.md), [`uptk_cl`](salt-outputs/uptk_cl.md), [`uptk_co3`](salt-outputs/uptk_co3.md), [`uptk_hco3`](salt-outputs/uptk_hco3.md) | Plant uptake | kg |
| [`dssl_total`](salt-outputs/dssl_total-routing-unit-salt-balance.md) | Total mineral dissolution | kg |

HRU salt output has a different 159-heading schema and is documented on the [HRU Salt](hru-salt.md) page.

## Channel salt

The `channel_salt_*` files use the common identifiers followed by these exact heading groups:

| Field | Description | Unit |
| --- | --- | --- |
| [`so4_in`](salt-outputs/so4_in.md), [`ca_in`](salt-outputs/ca_in.md), [`mg_in`](salt-outputs/mg_in.md), [`na_in`](salt-outputs/na_in.md), [`k_in`](salt-outputs/k_in.md), [`cl_in`](salt-outputs/cl_in.md), [`co3_in`](salt-outputs/co3_in.md), [`hco3_in`](salt-outputs/hco3_in.md) | Salt entering the channel | kg |
| [`so4_gw`](salt-outputs/so4_gw.md), [`ca_gw`](salt-outputs/ca_gw.md), [`mg_gw`](salt-outputs/mg_gw.md), [`na_gw`](salt-outputs/na_gw.md), [`k_gw`](salt-outputs/k_gw.md), [`cl_gw`](salt-outputs/cl_gw.md), [`co3_gw`](salt-outputs/co3_gw.md), [`hco3_gw`](salt-outputs/hco3_gw.md) | Groundwater salt entering the channel | kg |
| [`so4_out`](salt-outputs/so4_out.md), [`ca_out`](salt-outputs/ca_out.md), [`mg_out`](salt-outputs/mg_out.md), [`na_out`](salt-outputs/na_out.md), [`k_out`](salt-outputs/k_out.md), [`cl_out`](salt-outputs/cl_out.md), [`co3_out`](salt-outputs/co3_out.md), [`hco3_out`](salt-outputs/hco3_out.md) | Salt leaving the channel | kg |
| [`so4_seep`](salt-outputs/so4_seep.md), [`ca_seep`](salt-outputs/ca_seep.md), [`mg_seep`](salt-outputs/mg_seep.md), [`na_seep`](salt-outputs/na_seep.md), [`k_seep`](salt-outputs/k_seep.md), [`cl_seep`](salt-outputs/cl_seep.md), [`co3_seep`](salt-outputs/co3_seep.md), [`hco3_seep`](salt-outputs/hco3_seep.md) | Salt lost through channel seepage | kg |
| [`so4_irr`](salt-outputs/so4_irr.md), [`ca_irr`](salt-outputs/ca_irr.md), [`mg_irr`](salt-outputs/mg_irr.md), [`na_irr`](salt-outputs/na_irr.md), [`k_irr`](salt-outputs/k_irr.md), [`cl_irr`](salt-outputs/cl_irr.md), [`co3_irr`](salt-outputs/co3_irr.md), [`hco3_irr`](salt-outputs/hco3_irr.md) | Salt removed for irrigation | kg |
| [`so4_div`](salt-outputs/so4_div.md), [`ca_div`](salt-outputs/ca_div.md), [`mg_div`](salt-outputs/mg_div.md), [`na_div`](salt-outputs/na_div.md), [`k_div`](salt-outputs/k_div.md), [`cl_div`](salt-outputs/cl_div.md), [`co3_div`](salt-outputs/co3_div.md), [`hco3_div`](salt-outputs/hco3_div.md) | Salt removed by diversion | kg |
| [`so4_mass`](salt-outputs/so4_mass.md), [`ca_mass`](salt-outputs/ca_mass.md), [`mg_mass`](salt-outputs/mg_mass.md), [`na_mass`](salt-outputs/na_mass.md), [`k_mass`](salt-outputs/k_mass.md), [`cl_mass`](salt-outputs/cl_mass.md), [`co3_mass`](salt-outputs/co3_mass.md), [`hco3_mass`](salt-outputs/hco3_mass.md) | Salt stored in channel water | kg |
| [`so4_conc`](salt-outputs/so4_conc.md), [`ca_conc`](salt-outputs/ca_conc.md), [`mg_conc`](salt-outputs/mg_conc.md), [`na_conc`](salt-outputs/na_conc.md), [`k_conc`](salt-outputs/k_conc.md), [`cl_conc`](salt-outputs/cl_conc.md), [`co3_conc`](salt-outputs/co3_conc.md), [`hco3_conc`](salt-outputs/hco3_conc.md) | Salt concentration in channel water | g/m3 |

## Aquifer salt

The `aquifer_salt_*` files use these exact heading groups:

| Field | Description | Unit |
| --- | --- | --- |
| [`gw_so4`](salt-outputs/gw_so4.md), [`gw_ca`](salt-outputs/gw_ca.md), [`gw_mg`](salt-outputs/gw_mg.md), [`gw_na`](salt-outputs/gw_na.md), [`gw_k`](salt-outputs/gw_k.md), [`gw_cl`](salt-outputs/gw_cl.md), [`gw_co3`](salt-outputs/gw_co3.md), [`gw_hco3`](salt-outputs/gw_hco3.md) | Salt stored in groundwater | kg |
| [`rchg_so4`](salt-outputs/rchg_so4.md), [`rchg_ca`](salt-outputs/rchg_ca.md), [`rchg_mg`](salt-outputs/rchg_mg.md), [`rchg_na`](salt-outputs/rchg_na.md), [`rchg_k`](salt-outputs/rchg_k.md), [`rchg_cl`](salt-outputs/rchg_cl.md), [`rchg_co3`](salt-outputs/rchg_co3.md), [`rchg_hco3`](salt-outputs/rchg_hco3.md) | Salt entering with recharge | kg |
| [`seep_so4`](salt-outputs/seep_so4.md), [`seep_ca`](salt-outputs/seep_ca.md), [`seep_mg`](salt-outputs/seep_mg.md), [`seep_na`](salt-outputs/seep_na.md), [`seep_k`](salt-outputs/seep_k.md), [`seep_cl`](salt-outputs/seep_cl.md), [`seep_co3`](salt-outputs/seep_co3.md), [`seep_hco3`](salt-outputs/seep_hco3.md) | Salt leaving through aquifer seepage | kg |
| [`irr_so4`](salt-outputs/irr_so4.md), [`irr_ca`](salt-outputs/irr_ca.md), [`irr_mg`](salt-outputs/irr_mg.md), [`irr_na`](salt-outputs/irr_na.md), [`irr_k`](salt-outputs/irr_k.md), [`irr_cl`](salt-outputs/irr_cl.md), [`irr_co3`](salt-outputs/irr_co3.md), [`irr_hco3`](salt-outputs/irr_hco3.md) | Salt removed for irrigation | kg |
| [`div_so4`](salt-outputs/div_so4.md), [`div_ca`](salt-outputs/div_ca.md), [`div_mg`](salt-outputs/div_mg.md), [`div_na`](salt-outputs/div_na.md), [`div_k`](salt-outputs/div_k.md), [`div_cl`](salt-outputs/div_cl.md), [`div_co3`](salt-outputs/div_co3.md), [`div_hco3`](salt-outputs/div_hco3.md) | Salt removed by diversion | kg |
| [`mass_so4`](salt-outputs/mass_so4.md), [`mass_ca`](salt-outputs/mass_ca.md), [`mass_mg`](salt-outputs/mass_mg.md), [`mass_na`](salt-outputs/mass_na.md), [`mass_k`](salt-outputs/mass_k.md), [`mass_cl`](salt-outputs/mass_cl.md), [`mass_co3`](salt-outputs/mass_co3.md), [`mass_hco3`](salt-outputs/mass_hco3.md) | Aquifer salt mass | kg |
| [`conc_so4`](salt-outputs/conc_so4.md), [`conc_ca`](salt-outputs/conc_ca.md), [`conc_mg`](salt-outputs/conc_mg.md), [`conc_na`](salt-outputs/conc_na.md), [`conc_k`](salt-outputs/conc_k.md), [`conc_cl`](salt-outputs/conc_cl.md), [`conc_co3`](salt-outputs/conc_co3.md), [`conc_hco3`](salt-outputs/conc_hco3.md) | Groundwater concentration | g/m3 |
| [`dssl_total`](salt-outputs/dssl_total-aquifer-salt.md) | Salt dissolved from aquifer minerals | kg |

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
