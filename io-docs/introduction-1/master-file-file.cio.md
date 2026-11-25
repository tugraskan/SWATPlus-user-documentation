---
description: Master input file listing the filenames of core SWAT+ input files, optional climate directories, and the optional output directory.
---

# Master File (file.cio)

`file.cio` lists the filenames of core SWAT+ input files grouped into 25 category rows, followed by 5 climate-directory rows and an optional output-directory row. It is read at startup by [`readcio_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readcio_read.f90#L20-L125) into the structs in [`input_file_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/input_file_module.f90#L8-L317).

* **Title line and no header:** Line 1 is a non-blank title line (`character(len=80)`); there is **no** column header line.
* **Row order and category labels:** Lines 2–31 are read sequentially in fixed row order. The first token on each row (a `character(len=15)` category label) is read into `name` and discarded, not matched. Each filename field is `character(len=25)`.
* **Fixed slot counts:** The category rows use list-directed `read(107, *)`, so **every slot in a category row must contain a filename or `null`**. Omitting a slot causes Fortran to read onto the next line and shift all remaining categories (for example, `water_allocation` requires 2 entries: `place_of_use.wro` and `point_of_diver.wro`). On SWAT+ dev the `basin` row and the five climate-directory rows are read as whole lines instead (see below).
* **Missing `file.cio`:** If `file.cio` is absent from the working directory, SWAT+ retains the default filenames declared in [`input_file_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/input_file_module.f90#L8-L317) and writes outputs to the current working directory.

{% hint style="info" %}
Enter lowercase `null` instead of a filename when an optional file is not used (most readers perform a case-sensitive check against `"null"`).
{% endhint %}

## Input File Categories

#### Simulation

Read into `in_sim` ([`readcio_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readcio_read.f90#L26)):

1. [`time.sim`](simulation-settings/time.sim/README.md)
2. [`print.prt`](simulation-settings/print.prt/README.md)
3. [`object.prt`](simulation-settings/object.prt/README.md)
4. [`object.cnt`](simulation-settings/object.cnt/README.md)
5. [`constituents.cs`](constituents/constituents.cs.md)

#### Basin

Read into `in_basin` ([`readcio_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readcio_read.f90#L28-L41)):

1. [`codes.bsn`](basin-1/codes.bsn/README.md)
2. [`parameters.bsn`](basin-1/parameters.bsn/README.md)
3. [`carbon.bsn`](carbon/carbon.bsn/README.md) *(required when `codes.bsn` `carbon = 2`; its companion `<stem>_lyr.bsn` file is derived automatically by [`carbon_bsn_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_bsn_read.f90#L101-L110). On SWAT+ dev the row is read as one line: if it has only two file names, `carbon.bsn` keeps its default name, and the `climate` row is no longer consumed. Supplying `carbon.bsn` or `null` explicitly is still clearer.)*

#### Climate

Read into `in_cli` ([`readcio_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readcio_read.f90#L42)):

1. [`weather-sta.cli`](climate/weather-sta.cli/README.md)
2. [`weather-wgn.cli`](climate/weather-wgn.cli/README.md)
3. [`pet.cli`](climate/pet.cli/README.md) *(replaces the legacy commented-out `wind-dir.cli` slot in [`input_file_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/input_file_module.f90#L29-L30))*
4. [`pcp.cli`](climate/pcp.cli-and-precipitation-data-files.md)
5. [`tmp.cli`](climate/tmp.cli-and-temperature-data-files.md)
6. [`slr.cli`](climate/slr.cli-and-solar-radiation-data-files.md)
7. [`hmd.cli`](climate/hmd.cli-and-humidity-data-files.md)
8. [`wnd.cli`](climate/wnd.cli-and-wind-speed-data-files.md)
9. [`atmo.cli`](climate/atmo.cli/README.md) *(Fortran struct default `atmodep.cli`, commonly named `atmo.cli` in SWAT+ Editor)*

#### Connect

Read into `in_con` ([`readcio_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readcio_read.f90#L44)) and loaded by [`hyd_connect.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hyd_connect.f90#L127-L191); see [Connectivity](connectivity/README.md):

1. [`hru.con`](connectivity/hru.con/README.md)
2. [`hru-lte.con`](connectivity/hru.con/README.md)
3. [`rout_unit.con`](connectivity/hru.con/README.md)
4. [`gwflow.con`](connectivity/hru.con/README.md) *(read when `sp_ob%gwflow > 0`; see [GWFlow](modflow.md) for the `.gw` files opened directly from the working directory)*
5. [`aquifer.con`](connectivity/hru.con/README.md)
6. `aquifer2d.con` *(Note: In SWAT+ main (6f515368), this slot is parsed into `in_con%aqu2d_con` but is not used in simulation calculations).*
7. [`channel.con`](connectivity/hru.con/README.md) *(read when `sp_ob%chan > 0` for legacy SWAT channels)*
8. [`reservoir.con`](connectivity/hru.con/README.md)
9. [`recall.con`](connectivity/hru.con/README.md)
10. [`exco.con`](connectivity/hru.con/README.md)
11. [`delratio.con`](connectivity/hru.con/README.md)
12. [`outlet.con`](connectivity/hru.con/README.md)
13. [`chandeg.con`](connectivity/hru.con/README.md)

#### Channel

Read into `in_cha` ([`readcio_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readcio_read.f90#L46)):

1. [`initial.cha`](channels/initial.cha/README.md)
2. [`channel.cha`](channels/channel.cha/README.md) *(legacy SWAT channel objects)*
3. [`hydrology.cha`](channels/hydrology.cha/README.md) *(legacy SWAT channel objects)*
4. [`sediment.cha`](channels/sediment.cha/README.md) *(legacy SWAT channel objects)*
5. [`nutrients.cha`](channels/nutrients.cha/README.md)
6. [`channel-lte.cha`](channels/channel-lte.cha/README.md) *(SWAT-DEG channels)*
7. [`hyd-sed-lte.cha`](channels/hyd-sed-lte.cha/README.md) *(SWAT-DEG channel hydrology and sediment)*
8. [`temperature.cha`](channels/temperature.cha/README.md)

#### Reservoir

Read into `in_res` ([`readcio_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readcio_read.f90#L48)):

1. [`initial.res`](reservoirs/initial.res/README.md)
2. [`reservoir.res`](reservoirs/reservoir.res/README.md)
3. [`hydrology.res`](reservoirs/hydrology.res/README.md)
4. [`sediment.res`](reservoirs/sediment.res/README.md)
5. [`nutrients.res`](reservoirs/nutrients.res/README.md)
6. [`weir.res`](reservoirs/weir.res/README.md)
7. [`wetland.wet`](wetlands/wetland.wet/README.md)
8. [`hydrology.wet`](wetlands/hydrology.wet/README.md)

#### Routing Unit

Read into `in_ru` ([`readcio_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readcio_read.f90#L50)):

1. [`rout_unit.def`](routing-units/untitled-1/README.md)
2. [`rout_unit.ele`](routing-units/untitled-2/README.md)
3. [`rout_unit.rtu`](routing-units/untitled/README.md)
4. `rout_unit.dr` *(Note: In SWAT+ main (6f515368), this slot is parsed into `in_ru%ru_dr` but is not used in simulation calculations).*

#### HRU

Read into `in_hru` ([`readcio_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readcio_read.f90#L52)):

1. [`hru-data.hru`](hydrologic-response-units/hru-data.hru/README.md)
2. [`hru-lte.hru`](hydrologic-response-units/hru-lte.hru/README.md)

#### Export Coefficient

Read into `in_exco` ([`readcio_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readcio_read.f90#L54)) and loaded by [`exco_db_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_db_read.f90#L22-L42) when the corresponding constituent counts in `constituents.cs` are positive:

1. [`exco.exc`](point-sources-and-inlets/exco.exc/README.md)
2. [`exco_om.exc`](point-sources-and-inlets/exco_om.exc/README.md)
3. [`exco_pest.exc`](point-sources-and-inlets/exco_pest.exc/README.md)
4. [`exco_path.exc`](point-sources-and-inlets/exco_path.exc/README.md)
5. [`exco_hmet.exc`](point-sources-and-inlets/exco_hmet.exc/README.md)
6. [`exco_salt.exc`](point-sources-and-inlets/exco_salt.exc/README.md)

#### Recall

Read into `in_rec` ([`readcio_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readcio_read.f90#L56)):

1. [`recall.rec`](point-sources-and-inlets/recall.rec/README.md)

#### Delivery Ratio

Read into `in_delr` ([`readcio_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readcio_read.f90#L58)) and loaded by [`dr_db_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_db_read.f90#L22-L42):

1. [`delratio.del`](routing-units/delratio.del/README.md)
2. [`dr_om.del`](routing-units/dr_om.del/README.md)
3. [`dr_pest.del`](routing-units/dr_pest.del/README.md)
4. [`dr_path.del`](routing-units/dr_path.del/README.md)
5. [`dr_hmet.del`](routing-units/dr_hmet.del/README.md)
6. [`dr_salt.del`](routing-units/dr_salt.del/README.md)

#### Aquifer

Read into `in_aqu` ([`readcio_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readcio_read.f90#L60)):

1. [`initial.aqu`](aquifers/initial.aqu/README.md)
2. [`aquifer.aqu`](aquifers/aquifer.aqu/README.md)

#### Herd

Read into `in_herd` ([`readcio_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readcio_read.f90#L62)):

1. `animal.hrd`
2. `herd.hrd`
3. `ranch.hrd`

*(Note: In SWAT+ main (6f515368), all three `herd` slots are parsed into `in_herd` but are not used in simulation calculations).*

#### Water Allocation

Read into `in_wallo` ([`readcio_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readcio_read.f90#L64), [`input_file_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/input_file_module.f90#L144-L148)):

1. [`place_of_use.wro`](water-allocation/place_of_use.wro/README.md)
2. [`point_of_diver.wro`](water-allocation/point_of_diver.wro/README.md)

Both slots must be present on this row, using `null` when unused. Auxiliary `.wal` files are opened directly by fixed filename in the working directory; see [Water Allocation](water-allocation/README.md).

#### Link

Read into `in_link` ([`readcio_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readcio_read.f90#L66)):

1. [`chan-surf.lin`](connectivity/chan_surf.lin.md)
2. [`aqu_cha.lin`](connectivity/aqu_cha.lin.md)

#### Hydrology

Read into `in_hyd` ([`readcio_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readcio_read.f90#L68)):

1. [`hydrology.hyd`](hydrology/hydrology.hyd/README.md)
2. [`topography.hyd`](hydrology/topography.hyd/README.md)
3. [`field.fld`](hydrology/field.fld/README.md)

#### Structural

Read into `in_str` ([`readcio_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readcio_read.f90#L70)):

1. [`tiledrain.str`](structural-practices/tiledrain.str/README.md)
2. [`septic.str`](structural-practices/septic.str/README.md)
3. [`filterstrip.str`](structural-practices/filterstrip.str/README.md)
4. [`grassedww.str`](structural-practices/grassedww.str/README.md)
5. [`bmpuser.str`](structural-practices/bmpuser.str/README.md)

#### HRU Databases

Read into `in_parmdb` ([`readcio_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readcio_read.f90#L72)):

1. [`plants.plt`](databases/plants.plt/README.md)
2. [`fertilizer.frt`](databases/fertilizer.frt/README.md)
3. [`tillage.til`](databases/tillage.til/README.md)
4. [`pesticide.pes`](databases/pesticide.pes/README.md)
5. [`pathogens.pth`](databases/pathogens.pth/README.md) *(read by [`path_parm_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/path_parm_read.f90#L20-L25))*
6. `metals.mtl` *(Note: In SWAT+ main (6f515368), this slot is parsed into `in_parmdb%hmetcom_db` but is not used in simulation calculations).*
7. `salt.slt` *(Note: In SWAT+ main (6f515368), this slot is parsed into `in_parmdb%saltcom_db` but is not used in simulation calculations; active salt inputs are opened by fixed filename from the working directory).*
8. [`urban.urb`](databases/urban.urb/README.md)
9. [`septic.sep`](databases/septic.sep/README.md)
10. [`snow.sno`](hydrology/snow.sno/README.md)

#### Operation Scheduling

Read into `in_ops` ([`readcio_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readcio_read.f90#L74)):

1. [`harv.ops`](management-practices/harv.ops/README.md)
2. [`graze.ops`](management-practices/graze.ops/README.md)
3. [`irr.ops`](management-practices/irr.ops/README.md)
4. [`chem_app.ops`](management-practices/chem_app.ops/README.md)
5. [`fire.ops`](management-practices/fire.ops/README.md)
6. [`sweep.ops`](management-practices/sweep.ops/README.md)

#### Land Use Management

Read into `in_lum` ([`readcio_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readcio_read.f90#L76)):

1. [`landuse.lum`](landuse-and-management/landuse.lum/README.md)
2. [`management.sch`](landuse-and-management/management.sch/README.md)
3. [`cntable.lum`](landuse-and-management/cntable.lum/README.md)
4. [`cons_practice.lum`](landuse-and-management/cons_practice.lum/README.md)
5. [`ovn_table.lum`](landuse-and-management/ovn_table.lum/README.md)

#### Change

Read into `in_chg` ([`readcio_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readcio_read.f90#L78)) and loaded via [`proc_cal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/proc_cal.f90#L14-L35):

1. [`cal_parms.cal`](calibration/cal_parms.cal/README.md)
2. [`calibration.cal`](calibration/calibration.cal/README.md)
3. [`codes.sft`](calibration/codes.sft/README.md)
4. [`wb_parms.sft`](calibration/wb_parms.sft/README.md)
5. [`water_balance.sft`](calibration/water_balance.sft/README.md)
6. [`ch_sed_budget.sft`](calibration/ch_sed_budget.sft/README.md)
7. [`ch_sed_parms.sft`](calibration/ch_sed_parms.sft/README.md)
8. [`plant_parms.sft`](calibration/plant_parms.sft/README.md)
9. [`plant_gro.sft`](calibration/plant_gro.sft/README.md)

#### Initial

Read into `in_init` ([`readcio_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readcio_read.f90#L80)):

1. [`plant.ini`](landuse-and-management/plant.ini/README.md)
2. [`soil_plant.ini`](initialization/soil_plant.ini/README.md)
3. [`om_water.ini`](initialization/om_water.ini/README.md)
4. [`pest_hru.ini`](initialization/pest_hru.ini/README.md)
5. [`pest_water.ini`](initialization/pest_water.ini/README.md)
6. [`path_hru.ini`](initialization/path_hru.ini/README.md)
7. [`path_water.ini`](initialization/path_water.ini/README.md)
8. [`hmet_hru.ini`](initialization/hmet_hru.ini/README.md) *(parsed into memory by [`hmet_hru_aqu_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hmet_hru_aqu_read.f90#L21-L24), not used in simulation calculations)*
9. `hmet_water.ini` *(Note: In SWAT+ main (6f515368), this slot is parsed into `in_init%hmet_water` but is not used in simulation calculations).*
10. `salt_hru.ini` *(Note: In SWAT+ main (6f515368), this `file.cio` slot `in_init%salt_soil` is not used; [`salt_hru.ini`](initialization/salt_hru.ini/README.md) is opened directly by fixed filename in the working directory).*
11. `salt_water.ini` *(Note: In SWAT+ main (6f515368), this slot is parsed into `in_init%salt_water` but is not used in simulation calculations).*

#### Soils

Read into `in_sol` ([`readcio_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readcio_read.f90#L82)):

1. [`soils.sol`](soils/soils.sol/README.md)
2. [`nutrients.sol`](soils/nutrients.sol/README.md)
3. [`soils_lte.sol`](soils/soils_lte.sol/README.md) *(read by [`soil_lte_db_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_lte_db_read.f90#L21-L26); see reader caveat on its page)*

#### Conditional

Read into `in_cond` ([`readcio_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readcio_read.f90#L84)):

1. [`lum.dtl`](decision-tables/lum.dtl/README.md)
2. [`res_rel.dtl`](decision-tables/res_rel.dtl/README.md)
3. [`scen_lu.dtl`](decision-tables/scen_lu.dtl/README.md)
4. [`flo_con.dtl`](decision-tables/flo_con.dtl/README.md)

#### Regions

Read into `in_regs` ([`readcio_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readcio_read.f90#L86)); see [Landscape Units](landscape-units/README.md):

1. [`ls_unit.ele`](landscape-units/ls_unit.ele/README.md)
2. [`ls_unit.def`](landscape-units/ls_unit.def/README.md)
3. [`ls_reg.ele`](landscape-units/ls_reg.ele/README.md) *(reader [`reg_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reg_read_elements.f90#L1-L205) is uncalled in `6f515368`)*
4. [`ls_reg.def`](landscape-units/ls_reg.def/README.md) *(reader [`reg_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reg_read_elements.f90#L1-L205) is uncalled in `6f515368`)*
5. `ls_cal.reg` *(Note: In SWAT+ main (6f515368), this slot is parsed into `in_regs%cal_lcu` but is not used in simulation calculations).*
6. `ch_catunit.ele` *(Note: In SWAT+ main (6f515368), this slot is parsed into `in_regs%ele_cha` but is not used in simulation calculations; [`ch_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_elements.f90#L145) opens fixed-name [`element.ccu`](landscape-units/element.ccu/README.md) instead).*
7. [`ch_catunit.def`](landscape-units/ch_catunit.def/README.md)
8. [`ch_reg.def`](landscape-units/ch_reg.def/README.md)
9. [`aqu_catunit.ele`](landscape-units/aqu_catunit.ele/README.md)
10. [`aqu_catunit.def`](landscape-units/aqu_catunit.def/README.md)
11. `aqu_reg.def` *(checked with `inquire` in [`aqu_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_read_elements.f90#L86-L89), which then mistakenly opens `in_regs%def_aqu`)*
12. [`res_catunit.ele`](landscape-units/res_catunit.ele/README.md)
13. [`res_catunit.def`](landscape-units/res_catunit.def/README.md)
14. [`res_reg.def`](landscape-units/res_reg.def/README.md)
15. [`rec_catunit.ele`](landscape-units/rec_catunit.ele/README.md)
16. [`rec_catunit.def`](landscape-units/rec_catunit.def/README.md)
17. [`rec_reg.def`](landscape-units/rec_reg.def/README.md)

## Weather File Directories (Rows 26–30)

Rows 26–30 specify optional directories for weather data files when stored outside `TxtInOut` ([`readcio_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readcio_read.f90#L89-L98), [`input_file_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/input_file_module.f90#L286-L309)), each stored as `character(len=256)`:

1. `pcp` (`in_path_pcp%pcp`) — precipitation station files
2. `tmp` (`in_path_tmp%tmp`) — temperature station files
3. `slr` (`in_path_slr%slr`) — solar radiation station files
4. `hmd` (`in_path_hmd%hmd`) — relative humidity station files
5. `wnd` (`in_path_wnd%wnd`) — wind speed station files

{% hint style="info" %}
Enter `null` on each row when weather data files are stored in the project `TxtInOut` folder.
{% endhint %}

On SWAT+ dev each of these rows is read as a whole line by `read_cio_path` ([`readcio_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readcio_read.f90#L136-L196)):

* The first word is the label and is skipped. The value is the next word, or the text between matching quotes (`"..."` or `'...'`), so **quote a path that contains spaces**. A `/` no longer ends the value.
* A missing trailing separator is added: `\` when the `OS` environment variable contains `Windows`, otherwise `/`. `null` and an empty value are left as they are.
* The run stops with an error if the line is longer than 1024 characters, a quote is not closed, or the path is longer than 256 characters.

Each climate reader then opens `TRIM(ADJUSTL(in_path_*)) // filename` (e.g., [`cli_pmeas.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_pmeas.f90#L73-L76)).

Although `in_path_pet%peti` is declared in [`input_file_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/input_file_module.f90#L311-L314) and checked in [`cli_petmeas.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_petmeas.f90#L67-L70), [`readcio_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readcio_read.f90#L89-L98) has no row for it, so PET data files are always opened from the working directory.

## Output Directory (Optional Row 31)

An optional final row specifies the output directory ([`readcio_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readcio_read.f90#L101-L118), [`output_path_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_path_module.f90#L11-L166)):

* [`readcio_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readcio_read.f90#L103-L117) reads the entire line as raw text (`'(A)'`, `line_buffer` up to 512 characters) so spaces and `/` characters do not break list-directed parsing, strips the first space-delimited label word (e.g., `output_path`), and passes the remainder (up to 256 characters) to `init_output_path`.
* If this row is omitted, blank, `null`, or `NULL`, outputs are written to the current working directory.
* Otherwise, `init_output_path` converts path separators for the host OS, automatically appends a trailing separator, creates the directory if needed, and stops with an error if the directory cannot be created or accessed (or if a Windows drive path containing `:` is supplied on Unix). Output files opened through `open_output_file` are written to this directory.

## Fixed-Filename Input Files Not Listed in `file.cio`

Several optional module files are opened directly by fixed filename in `TxtInOut` rather than listed in `file.cio`, including `carbon_lyr.bsn` (derived from `carbon.bsn`), [`soil_test.sol`](soils/soil_test.sol/README.md) (SWAT+ dev, `carbon = 2`), [`carbon_layers.prt`](simulation-settings/carbon_layers.prt/README.md), [`co2_yr.dat`](climate/co2_yr.dat/README.md), [`shade_factor.shf`](channels/shade_factor.shf/README.md) (`in_shf%ssff_shf` in [`input_file_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/input_file_module.f90#L281-L284) is never read from `file.cio`), [GWFlow](modflow.md) `*.gw` files, auxiliary `.wal` [Water Allocation](water-allocation/README.md) files, [`scen_dtl.upd`](calibration/scen_dtl.upd/README.md), [`soil_lyr_depths.sol`](soils/soil_lyr_depths.sol/README.md), [`satbuffer.str`](structural-practices/satbuffer.str/README.md), [`puddle.ops`](landuse-and-management/puddle.ops/README.md), [`transplant.ops`](landuse-and-management/transplant.ops/README.md), [`manure_allo.mnu`](landuse-and-management/manure_allo.mnu/README.md), [`element.ccu`](landscape-units/element.ccu/README.md), and salt/general-constituent working-directory files (see [Initialization](initialization/README.md)).
