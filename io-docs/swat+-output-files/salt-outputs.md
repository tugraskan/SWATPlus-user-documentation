# Salt Outputs

SWAT+ can report salt balances for the basin, routing units, HRUs, channels, aquifers, reservoirs, and wetlands. These files are produced only when the salt module is configured and the corresponding print option is enabled. Daily, monthly, yearly, and average-annual files use the suffixes `_day`, `_mon`, `_yr`, and `_aa`; TXT and CSV variants share the same data headings.

The salt ions always appear in this order: sulfate (`so4`), calcium (`ca`), magnesium (`mg`), sodium (`na`), potassium (`k`), chloride (`cl`), carbonate (`co3`), and bicarbonate (`hco3`). Every name in the Field column below is an exact printed heading.

Unless a section states otherwise, daily, monthly, and yearly mass fields are printed in kg for the reporting interval. In average-annual files, the printed units row labels flux fields as kg/yr. Stored mass remains a state value, although some average-annual preambles also print kg/yr for those headings; the tables below reproduce the source-defined output rather than reinterpreting it. Concentrations are printed in g/m3.

The common identifying headings are `jday`, `mon`, `day`, `yr`, `unit`, and `gis_id`. Basin salt output instead begins with `yr`, `mo`, and `jday`.

## Basin salt balance

The files are `basin_salt_day`, `basin_salt_mon`, `basin_salt_yr`, and `basin_salt_aa` with `.txt` and `.csv` variants. Each mass-balance heading represents the total of all eight ions.

| Field | Description | Unit |
| --- | --- | --- |
| `lat_kg`, `gw_kg`, `sur_kg`, `urb_kg`, `wet_kg`, `tile_kg` | Salt reaching streams through lateral flow, groundwater, surface runoff, urban runoff, wetlands, and tile drainage | kg |
| `perc_kg`, `gwup_kg`, `wtsp_kg` | Soil-aquifer and wetland-soil salt transfers | kg |
| `irsw_kg`, `irgw_kg`, `irwo_kg` | Salt added by surface-water, groundwater, and outside-source irrigation | kg |
| `rain_kg`, `dryd_kg`, `road_kg`, `fert_kg`, `amnd_kg` | Salt inputs from rain, dry deposition, road salt, fertilizer, and amendments | kg |
| `uptk_kg` | Salt removed by plant uptake | kg |
| `ptso_kg`, `ptout_kg` | Point-source salt entering and leaving the basin | kg |
| `rchg_kg`, `seep_kg` | Aquifer recharge and seepage salt transfers | kg |
| `dssl_kg`, `dsaq_kg` | Mineral dissolution in soils and aquifers | kg |
| `soilds_kg`, `soilmn_kg`, `aquds_kg`, `aqumn_kg` | Dissolved and mineral salt storage in soils and aquifers | kg |

## Routing-unit salt balance

The `rout_unit_salt_*` files report the eight ions for each of these exact heading groups:

| Field | Description | Unit |
| --- | --- | --- |
| `total_so4`, `total_ca`, `total_mg`, `total_na`, `total_k`, `total_cl`, `total_co3`, `total_hco3` | Total salt load from the routing unit | kg |
| `perc_so4`, `perc_ca`, `perc_mg`, `perc_na`, `perc_k`, `perc_cl`, `perc_co3`, `perc_hco3` | Percolation | kg |
| `surq_so4`, `surq_ca`, `surq_mg`, `surq_na`, `surq_k`, `surq_cl`, `surq_co3`, `surq_hco3` | Surface runoff | kg |
| `latq_so4`, `latq_ca`, `latq_mg`, `latq_na`, `latq_k`, `latq_cl`, `latq_co3`, `latq_hco3` | Lateral flow | kg |
| `tile_so4`, `tile_ca`, `tile_mg`, `tile_na`, `tile_k`, `tile_cl`, `tile_co3`, `tile_hco3` | Tile flow | kg |
| `wtsp_so4`, `wtsp_ca`, `wtsp_mg`, `wtsp_na`, `wtsp_k`, `wtsp_cl`, `wtsp_co3`, `wtsp_hco3` | Wetland seepage | kg |
| `irsw_so4`, `irsw_ca`, `irsw_mg`, `irsw_na`, `irsw_k`, `irsw_cl`, `irsw_co3`, `irsw_hco3` | Surface-water irrigation | kg |
| `irgw_so4`, `irgw_ca`, `irgw_mg`, `irgw_na`, `irgw_k`, `irgw_cl`, `irgw_co3`, `irgw_hco3` | Groundwater irrigation | kg |
| `irwo_so4`, `irwo_ca`, `irwo_mg`, `irwo_na`, `irwo_k`, `irwo_cl`, `irwo_co3`, `irwo_hco3` | Outside-source irrigation | kg |
| `rain_so4`, `rain_ca`, `rain_mg`, `rain_na`, `rain_k`, `rain_cl`, `rain_co3`, `rain_hco3` | Rainfall input | kg |
| `dryd_so4`, `dryd_ca`, `dryd_mg`, `dryd_na`, `dryd_k`, `dryd_cl`, `dryd_co3`, `dryd_hco3` | Dry deposition | kg |
| `road_so4`, `road_ca`, `road_mg`, `road_na`, `road_k`, `road_cl`, `road_co3`, `road_hco3` | Road-salt application | kg |
| `fert_so4`, `fert_ca`, `fert_mg`, `fert_na`, `fert_k`, `fert_cl`, `fert_co3`, `fert_hco3` | Fertilizer input | kg |
| `amnd_so4`, `amnd_ca`, `amnd_mg`, `amnd_na`, `amnd_k`, `amnd_cl`, `amnd_co3`, `amnd_hco3` | Amendment input | kg |
| `uptk_so4`, `uptk_ca`, `uptk_mg`, `uptk_na`, `uptk_k`, `uptk_cl`, `uptk_co3`, `uptk_hco3` | Plant uptake | kg |
| `dssl_total` | Total mineral dissolution | kg |

HRU salt output has a different 159-heading schema and is documented on the [HRU Salt](hru-salt.md) page.

## Channel salt

The `channel_salt_*` files use the common identifiers followed by these exact heading groups:

| Field | Description | Unit |
| --- | --- | --- |
| `so4_in`, `ca_in`, `mg_in`, `na_in`, `k_in`, `cl_in`, `co3_in`, `hco3_in` | Salt entering the channel | kg |
| `so4_gw`, `ca_gw`, `mg_gw`, `na_gw`, `k_gw`, `cl_gw`, `co3_gw`, `hco3_gw` | Groundwater salt entering the channel | kg |
| `so4_out`, `ca_out`, `mg_out`, `na_out`, `k_out`, `cl_out`, `co3_out`, `hco3_out` | Salt leaving the channel | kg |
| `so4_seep`, `ca_seep`, `mg_seep`, `na_seep`, `k_seep`, `cl_seep`, `co3_seep`, `hco3_seep` | Salt lost through channel seepage | kg |
| `so4_irr`, `ca_irr`, `mg_irr`, `na_irr`, `k_irr`, `cl_irr`, `co3_irr`, `hco3_irr` | Salt removed for irrigation | kg |
| `so4_div`, `ca_div`, `mg_div`, `na_div`, `k_div`, `cl_div`, `co3_div`, `hco3_div` | Salt removed by diversion | kg |
| `so4_mass`, `ca_mass`, `mg_mass`, `na_mass`, `k_mass`, `cl_mass`, `co3_mass`, `hco3_mass` | Salt stored in channel water | kg |
| `so4_conc`, `ca_conc`, `mg_conc`, `na_conc`, `k_conc`, `cl_conc`, `co3_conc`, `hco3_conc` | Salt concentration in channel water | g/m3 |

## Aquifer salt

The `aquifer_salt_*` files use these exact heading groups:

| Field | Description | Unit |
| --- | --- | --- |
| `gw_so4`, `gw_ca`, `gw_mg`, `gw_na`, `gw_k`, `gw_cl`, `gw_co3`, `gw_hco3` | Salt stored in groundwater | kg |
| `rchg_so4`, `rchg_ca`, `rchg_mg`, `rchg_na`, `rchg_k`, `rchg_cl`, `rchg_co3`, `rchg_hco3` | Salt entering with recharge | kg |
| `seep_so4`, `seep_ca`, `seep_mg`, `seep_na`, `seep_k`, `seep_cl`, `seep_co3`, `seep_hco3` | Salt leaving through aquifer seepage | kg |
| `irr_so4`, `irr_ca`, `irr_mg`, `irr_na`, `irr_k`, `irr_cl`, `irr_co3`, `irr_hco3` | Salt removed for irrigation | kg |
| `div_so4`, `div_ca`, `div_mg`, `div_na`, `div_k`, `div_cl`, `div_co3`, `div_hco3` | Salt removed by diversion | kg |
| `mass_so4`, `mass_ca`, `mass_mg`, `mass_na`, `mass_k`, `mass_cl`, `mass_co3`, `mass_hco3` | Aquifer salt mass | kg |
| `conc_so4`, `conc_ca`, `conc_mg`, `conc_na`, `conc_k`, `conc_cl`, `conc_co3`, `conc_hco3` | Groundwater concentration | g/m3 |
| `dssl_total` | Salt dissolved from aquifer minerals | kg |

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
