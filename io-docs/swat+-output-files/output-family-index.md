# Output Family Index

This index groups SWAT+ outputs by their actual printed schema. A family normally has daily (`_day`), monthly (`_mon`), yearly (`_yr`), and average-annual (`_aa`) variants. When CSV output is enabled, `.txt` and `.csv` generally share the same data headings, but TXT files may include explanatory lines before the header.

The family names below describe the files opened by the current source. An output is created only when its model component, constituent, and print option are active.

## Landscape and basin

| Family | Documentation |
| --- | --- |
| `basin_wb_*`, `lsunit_wb_*`, `hru_wb_*`, `hru-lte_wb_*` | [Water Balance](water-balance.md) |
| `basin_nb_*`, `lsunit_nb_*`, `hru_nb_*` | [Nutrient Balance](nutrient-balance.md) |
| `basin_ls_*`, `lsunit_ls_*`, `hru_ls_*`, `hru-lte_ls_*` | [Losses](losses.md) |
| `basin_pw_*`, `lsunit_pw_*`, `hru_pw_*`, `hru-lte_pw_*` | [Plant and Weather](plant-and-weather.md) |
| `basin_crop_yld_*`, `crop_yld_*` | [Plant and Weather](plant-and-weather.md) |
| `mgt_out.txt`, `lu_change_out.txt` | [Management](management.md) |
| `hru_begsim_soil_prop.*`, `hru_endsim_soil_prop.*` | [Soil](soil.md) |

## Routed water and sediment

| Family | Documentation |
| --- | --- |
| `channel_sd_*`, `channel_sdmorph_*`, basin equivalents | [Channel](channel.md) |
| `channel_*`, `basin_cha_*` | [Channel](channel.md) |
| `sd_chanbud_*`, `basin_sd_chanbud_*`, `ch_sedbud_*`, `chanbud_order_*`, `sedbud_*` | [Channel Sediment Budgets](channel-sediment-budgets.md) |
| `reservoir_*`, `basin_res_*` | [Reservoir](reservoir.md) |
| `wetland_*` | [Wetland](wetland.md) |
| `aquifer_*`, `basin_aqu_*` | [Aquifer](aquifer.md) |
| `ru_*` | [Routing Unit](routing-unit.md) |
| `recall_*`, `basin_psc_*` | [Recall](recall.md) |
| `hydin_*`, `hydout_*`, `deposition_*` | [Hydrographs](hydrographs.md) |

## Constituents

| Family | Documentation |
| --- | --- |
| `hru_salt_*` | [HRU Salt](hru-salt.md) |
| `basin_salt_*`, `rout_unit_salt_*`, `channel_salt_*`, `aquifer_salt_*`, `reservoir_salt_*`, `wetland_salt_*` | [Salt Outputs](salt-outputs.md) |
| `hru_cs_*`, `rout_unit_cs_*`, `channel_cs_*`, `aquifer_cs_*`, `reservoir_cs_*`, `wetland_cs_*`, `basin_cs_*` | [Conservative Constituents](conservative-constituents.md) |
| `hru_pest_*`, routed-object pesticide families, and basin equivalents | [Pesticides](pesticides.md) |
| `hru_path_*` | [Pathogen Outputs](pathogens.md) |
| `hydin_salts_*`, `hydout_salts_*`, pesticide, pathogen, and metal variants | [Hydrologic Constituent Streams](hydrologic-constituent-streams.md) |

## Water allocation and groundwater

| Family | Documentation |
| --- | --- |
| `water_allo_*`, `wallo_use_*`, `wallo_treat_*` | [Water Allocation](water-allocation.md) |
| `gwflow_basin_wb_*` | [GWFlow Basin Water Balance](gwflow-basin-water-balance.md) |
| GWFlow cell, observation, pumping, heat, canal, pond, and configured-group reports | [GWFlow Outputs](gwflow-outputs.md) |

## Carbon and nitrogen

Modern and legacy carbon/nitrogen reports include `hru_ncycle_*`, `hru_carb_gl_*`, `hru_scf_*`, `lsu_carb_gl_*`, `lsu_scf_*`, `hru_totc.*`, `basin_totc.*`, and the dynamic layer/status reports under `hru_carbvars.*`, `hru_org_*_vars.*`, `hru_cbn_lyr.*`, and `hru_seq_lyr.*`. See [Modern Carbon and Nitrogen Outputs](carbon/modern-carbon-nitrogen.md) and the [carbon output overview](carbon/README.md). Layered and legacy files must be interpreted with their printed `freq`, `soil_lyr`, and `soil_depth` columns.

## Dynamic and diagnostic outputs

Configured [Object Outputs](object-outputs.md), the [Flow Duration Curve](flow-duration-curve.md), and [Debugging Outputs](debugging-outputs.md) do not share the normal fixed time-series schema. Their columns can depend on object selection, observations, layers, or diagnostic context.

Files such as `simulation.out`, `diagnostics.out`, `checker.out`, `files_out.out`, `area_calc.out`, `hydcon.out`, `co2.out`, `paddy_test.csv`, and `yield.out` are specialized status, diagnostic, test, or legacy reports. Their presence in source does not mean they are normal user-selectable output tables.
