# Output Family Index

This index maps filename families in SWAT+ revision `6f515368` to their reference pages. The common time-series suffixes are `_day`, `_mon`, `_yr`, and `_aa`. See each family page for its intervals, activation conditions, and row layouts. See [Output File Format](output-file-format.md) for preambles and TXT and CSV differences.

## Landscape and basin

| Family | Documentation |
| --- | --- |
| `basin_wb_*`, `lsunit_wb_*`, `hru_wb_*`, `hru-lte_wb_*` | [Water Balance](water-balance/README.md) |
| `basin_nb_*`, `lsunit_nb_*`, `hru_nb_*` | [Nutrient Balance](nutrient-balance/README.md) |
| `basin_ls_*`, `lsunit_ls_*`, `hru_ls_*`, `hru-lte_ls_*` | [Losses](losses/README.md) |
| `basin_pw_*`, `lsunit_pw_*`, `hru_pw_*`, `hru-lte_pw_*` | [Plant and Weather](plant-and-weather/README.md) |
| `basin_crop_yld_*`, `crop_yld_*` | [Plant and Weather](plant-and-weather/README.md) |
| `mgt_out.txt`, `lu_change_out.txt` | [Management](management/README.md) |
| `hru_begsim_soil_prop.*`, `hru_endsim_soil_prop.*` | [Soil](soil/README.md) |

## Routed water and sediment

| Family | Documentation |
| --- | --- |
| `channel_sd_*`, `channel_sdmorph_*`, `basin_sd_chamorph_*` | [Channel](channel/README.md) |
| `basin_sd_cha_*` | [Basin SD Channel General Output](channel/basin-sd-channel-general.md) |
| `channel_*`, `basin_cha_*` | [Channel](channel/README.md) |
| `sd_chanbud_*`, `basin_sd_chanbud_*`, `ch_sedbud_*`, `chanbud_order_*`, `sedbud_*` | [Channel Sediment Budgets](channel-sediment-budgets/README.md) |
| `reservoir_*`, `basin_res_*` | [Reservoir](reservoir/README.md) |
| `wetland_*` | [Wetland](wetland/README.md) |
| `aquifer_*`, `basin_aqu_*` | [Aquifer](aquifer/README.md) |
| `ru_*` | [Routing Unit](routing-unit/README.md) |
| `recall_*`, `basin_psc_*` | [Recall](recall/README.md) |
| `hydin_*`, `hydout_*`, `deposition_*` | [Hydrographs](hydrographs/README.md); [Deposition schema](hydrographs/deposition.md) |

The `ch_sedbud_*` and `chanbud_order_*` files use `_d`, `_m`, `_y`, and `_a` for their time suffixes. [Channel sediment budget opener](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_sd_channel.f90#L350) · [Order budget opener](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_sd_channel.f90#L282)

## Constituents

| Family | Documentation |
| --- | --- |
| `hru_salt_*` | [HRU Salt](hru-salt/README.md) |
| `basin_salt_*`, `rout_unit_salt_*`, `channel_salt_*`, `aquifer_salt_*`, `reservoir_salt_*`, `wetland_salt_*` | [Salt Outputs](salt-outputs/README.md) |
| `hru_cs_*`, `rout_unit_cs_*`, `channel_cs_*`, `aquifer_cs_*`, `reservoir_cs_*`, `wetland_cs_*`, `basin_cs_*` | [Conservative Constituents](conservative-constituents/README.md) |
| `hru_pest_*`, routed-object pesticide families, and basin equivalents | [Pesticides](pesticides/README.md) |
| `hru_path_*` | [Pathogen Outputs](pathogens/README.md) |
| `hydin_salts_*`, `hydout_salts_*`, pesticide, pathogen, and metal variants defined by dormant routines | [Hydrologic Constituent Streams](hydrologic-constituent-streams/README.md) |

## Water allocation and groundwater

| Family | Documentation |
| --- | --- |
| `water_allo_*`, `wallo_use_*`, `wallo_treat_*` | [Water Allocation](water-allocation/README.md) |
| `gwflow_basin_wb_*` | [GWFlow Basin Water Balance](gwflow-basin-water-balance/README.md) |
| GWFlow cell, observation, pumping, heat, canal, pond, and configured-group reports | [GWFlow Outputs](gwflow-outputs/README.md) |

## Carbon and nitrogen

Modern and legacy carbon/nitrogen reports include `hru_ncycle_*`, `hru_carb_gl_*`, `hru_scf_*`, `lsu_carb_gl_*`, `lsu_scf_*`, `hru_plc_stat_*`, `lsu_plc_stat_*`, `hru_totc.*`, `basin_totc.*`, and the dynamic layer/status reports under `hru_carbvars.*`, `hru_org_*_vars.*`, `hru_cbn_lyr.*`, and `hru_seq_lyr.*`. See [Modern Carbon and Nitrogen Outputs](carbon/modern-carbon-nitrogen.md) and the [carbon output overview](carbon/README.md). Layered and legacy reports use fields such as `freq`, `soil_lyr`, and `soil_depth` according to the specific writer. The `hru_ncycle_*` openers write titles, headings, and units. The pinned source trace found no data-row writer for their eight file units. [Nutrient-cycling openers](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_init.f90#L117)

## Dynamic and diagnostic outputs

[Object Outputs](object-outputs.md) use request-specific names and layouts. [Flow Duration Curve](flow-duration-curve/README.md) covers the end-of-simulation summary in `flow_duration_curve.out`. [Debugging Outputs](debugging-outputs.md) covers the run log, registry, setup checks, and specialized files.
