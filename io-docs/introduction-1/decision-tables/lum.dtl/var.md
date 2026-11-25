---
description: Condition variable
---

# var

**Code reference:** `dtbl_lum(i)%cond(ic)%var` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditional_module.f90#L8)).

Keyword that selects what the condition tests. The same list serves every decision table file. Spell it exactly: an unrecognized keyword matches no branch, the row restricts nothing, and no warning is written. [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L62-L65) · [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L847-L848)

| Keyword | Quantity tested | Uses | Source |
| ------- | --------------- | ---- | ------ |
| `w_stress`, `n_stress`, `p_stress` | Mean stress factor of growing plants (1 = no stress; with none growing `w_stress` is 1, the others 0) | ob_num, lim_const | [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L67-L119) |
| `phu_plant` | Plant's fraction of potential heat units; first plant that has accumulated any | ob_num, lim_const | [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L122-L142) |
| `phu_base0` | Fraction of annual base-0 heat units | ob, ob_num, lim_const | [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L145-L157) |
| `precip_cur`, `precip_next` | Precipitation today or tomorrow (mm) | ob, ob_num, lim_const | [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L160-L187) |
| `plant_gro` | Plant is growing | lim_const = plant position (minimum 1) | [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L190-L200) |
| `plant_name_gro` | Named plant is growing | lim_var = plant | [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L203-L222) |
| `days_plant`, `days_harv`, `days_irr` | Days since planting, harvest, irrigation | lim_const | [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L226-L250) |
| `days_act` | Counter since an action; compared with lim_const + 2 | lim_var = action name | [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L253-L260) |
| `day_start` | Starting day of the simulation from time.sim (a fixed value) | lim_const | [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L263-L266) |
| `irr_year` | Irrigation applied (mm), accumulated over the whole run | lim_const | [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L269-L273) |
| `slope` | HRU slope (m/m) | lim_const | [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L276-L280) |
| `soil_water` | Profile soil water (mm) | lim_var, lim_op, lim_const | [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L283-L310) |
| `jday`, `month` | Day of year, month | lim_const | [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L313-L322) |
| `year_rot` | Rotation year | lim_const | [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L325-L331) |
| `year_gro`, `cur_yrs_mat` | Years to maturity counter of the first plant | lim_const | [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L334-L340) |
| `year_cal`, `year_seq`, `year_start` | Calendar year, simulation year number, first calendar year | lim_const | [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L343-L358) |
| `biomass`, `ground_cov` | Above-ground plant biomass (kg/ha); `ground_cov` does not add residue | lim_const | [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L370-L388) |
| `leaf_area` | Leaf area index | lim_const | [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L377-L381) |
| `p_factor`, `k_factor` | USLE P factor; USLE K of the top layer | lim_const | [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L391-L402) |
| `hyd_soil_group` | Hydrologic soil group | lim_var | [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L405-L414) |
| `p_pet` | Weather-generator precipitation/PET ratio | lim_const | [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L417-L422) |
| `p_lab_150` | Labile P indicator for the upper soil (uses at most layers 1 and 2) | lim_const | [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L425-L444) |
| `soil_temp2`, `soil_carbon` | Temperature of layer 2; carbon of layer 1 | lim_const | [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L447-L458) |
| `tile_drained` | HRU has tile drains (`=`) or not (`/`) | alternative token | [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L461-L476) |
| `prob` | Uniform random number from 0 to 1 | lim_const | [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L479-L483) |
| `prob_unif` | One random day in a window | [frac_app](frac_app.md), ob_num, lim_const | [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L486-L525) |
| `prob_unif1` | Rising daily probability from 1 January of year ob_num over lim_const days | ob_num, lim_const | [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L528-L555) |
| `prob_unif_lu` | Spreads events over a day window across HRUs of a land use | ob_num, lim_const, plus a `land_use` row | [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L558-L608) |
| `channel_flo` | Current outflow hydrograph as m³/s; ob_num does not select it | lim_const | [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L611-L617) |
| `tile_flo` | Daily tile flow (mm) | ob_num, lim_const | [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L620-L624) |
| `irr_demand`, `irr_pou_dmd` | Irrigation demand of an HRU or place of use (m³) | ob_num, lim_const | [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L627-L638) |
| `aqu_dep` | Depth to water table (m) | ob_num, lim_const | [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L641-L645) |
| `land_use`, `cal_group` | Land use name; calibration group | lim_var | [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L648-L670) |
| `tillage` | HRU schedule includes the named decision table | lim_var | [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L672-L688) |
| `plant_com` | Plant is (`=`) or is not (`/`) in the community | lim_var | [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L691-L717) |
| `ch_order` | Channel order | lim_const | [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L720-L730) |
| `wtow_vol` | Water tower storage compared with a fraction of capacity | ob_num, lim_const | [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L733-L741) |
| `vol` | Reservoir storage (m³) | lim_var, lim_op, lim_const | [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L744-L782) |
| `res_inflo` | Reservoir inflow (m³/s) | ob_num, lim_const | [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L785-L791) |
| `wet_depth`, `weirh` | Ponded depth; weir height (enter mm) | ob_num, lim_const | [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L794-L815) |
| `vol_wet` | Wetland storage (m³) | lim_var, lim_op, lim_const | [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L820-L845) |

For `days_act`, the reader matches the limit variable against action names in the same table. A name that matches no action leaves the index at 0, which is then used to read the counter array. [`dtbl_lum_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dtbl_lum_read.f90#L298-L303) · [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L253-L260)
