---
description: Objects that output can be printed for at different time steps
---

# object

**Code reference:** `name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_print_codes_read.f90#L11)).

The table below lists the objects that are listed in the first column of this section of the **print.prt** file. For each of these objects, output can be printed at daily, monthly, yearly, and average annual time steps by entering y (=yes) or n (=no) in the following four columns.

{% hint style="info" %}
The user is advised to print only those outputs that are needed for model evaluation or further analysis. Especially daily printing can result in very large output files that may exceed hard drive storage.
{% endhint %}

| Object          | Definition                                                     |
| --------------- | -------------------------------------------------------------- |
| basin\_wb       | Basin water balance                                            |
| basin\_nb       | Basin nutrient balance                                         |
| basin\_ls       | Basin losses                                                   |
| basin\_pw       | Basin plant and weather                                        |
| basin\_aqu      | Basin aquifer                                                  |
| basin\_res      | Basin reservoir                                                |
| basin\_cha | Basin channel output |
| basin\_sd\_cha  | Basin SWAT-DEG channel                                         |
| basin\_psc      | Basin point sources                                            |
| region\_wb      | Currently not used                                             |
| region\_nb      | Currently not used                                             |
| region\_ls      | Currently not used                                             |
| region\_pw      | Currently not used                                             |
| region\_aqu     | Currently not used                                             |
| region\_res     | Currently not used                                             |
| region\_sd\_cha | Currently not used                                             |
| region\_psc     | Currently not used                                             |
| water\_allo     | Water allocation (also gates manure allocation source and demand outputs in [`manure_source_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/manure_source_output.f90#L19) and [`manure_demand_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/manure_demand_output.f90#L22)) |
| lsunit\_wb      | Landscape unit water balance                                   |
| lsunit\_nb      | Landscape unit nutrient balance                                |
| lsunit\_ls      | Landscape unit losses                                          |
| lsunit\_pw      | Landscape unit plant and weather                               |
| hru\_wb         | HRU water balance                                              |
| hru\_nb         | HRU nutrient balance                                           |
| hru\_ls         | HRU losses                                                     |
| hru\_pw         | HRU plant and weather                                          |
| hru-lte\_wb     | HRU-lte water balance                                          |
| hru-lte\_nb     | Not used (no nutrient processes simulated for HRU-lte objects) |
| hru-lte\_ls     | HRU-lte losses                                                 |
| hru-lte\_pw     | HRU-lte plant and weather                                      |
| channel | Channel output |
| channel\_sd     | SWAT-DEG channel output                                        |
| aquifer         | Aquifer output                                                 |
| reservoir       | Reservoir output                                               |
| recall          | Point source output                                            |
| hyd             | Incoming and outgoing hydrographs (`hydin_*`, `hydout_*`, and `deposition_*`; [`header_hyd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_hyd.f90#L19-L204)) |
| ru              | Routing unit output                                            |
| pest            | Pesticide output for all objects and basin                     |
| basin\_salt     | Basin salt balance                                             |
| hru\_salt       | HRU salt fluxes and state variables                            |
| ru\_salt        | Routing unit salt output                                       |
| aqu\_salt       | Aquifer salt output                                            |
| channel\_salt   | Channel salt output                                            |
| res\_salt       | Reservoir salt output (also gates wetland salt data rows in [`wet_salt_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_salt_output.f90#L41)) |
| wetland\_salt   | Wetland salt output (opens headers in [`header_salt.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_salt.f90#L854-L944); data rows check `res_salt`) |
| basin\_cs       | Basin constituent balance                                      |
| hru\_cs         | HRU constituent fluxes and state variables                     |
| ru\_cs          | Routing unit constituent output                                |
| aqu\_cs         | Aquifer constituent output                                     |
| channel\_cs     | Channel constituent output                                     |
| res\_cs         | Reservoir constituent output (also gates wetland constituent files in [`header_const.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L882-L978) and [`wet_cs_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_cs_output.f90#L43)) |
| wetland\_cs     | Parsed into `pco%cs_wet` but not read by output writers in SWAT+ main (`6f515368`); wetland constituent output is gated by `res_cs` |
| lsu\_cb\_gl | LSU-area-weighted carbon gain/loss |
| lsu\_cb\_trf | LSU-area-weighted carbon transformations |
| lsu\_cb\_plt | LSU-area-weighted plant carbon state |
| hru\_cb | Legacy HRU carbon output (active daily, monthly, and yearly writer calls) |
| hru\_cb\_vars | Legacy HRU carbon-variable output (active daily, monthly, and yearly writer calls when carbon = 2) |
| hru\_cb\_gl | HRU carbon gain/loss |
| hru\_cb\_trf | HRU carbon transformations |
| hru\_cb\_lyr | HRU per-layer soil organic carbon totals and sequestration |
| hru\_cb\_cpool | HRU per-layer carbon pools |
| hru\_cb\_npool | HRU per-layer nitrogen and phosphorus pools |
| hru\_cb\_plt | HRU plant carbon state |
| hru\_cb\_flux | HRU per-layer carbon-flux diagnostics |
| hru\_cb\_drv | HRU per-layer carbon-driver diagnostics |
| hru\_cb\_dyn | HRU per-layer carbon-dynamics diagnostics |
| hru\_cb\_snap | HRU soil-property snapshot |
| gwflow\_wb | GWFlow cell and basin water-balance output |
| gwflow\_flux | GWFlow canal, pond, tile, groundwater-surface-water, and channel-observation flux output |
| gwflow\_heat | GWFlow basin heat-balance output |
| gwflow\_solute | GWFlow basin solute-balance output |
| gwflow\_obs | GWFlow observation-well output |
| gwflow\_pump | GWFlow HRU pumping output |

Label-based object parsing (`use_obj_lbls` set to a value other than `n`) is required for `lsu_cb_*`, `hru_cb*`, and `gwflow_*` rows because fixed-order parsing in [`basin_print_codes_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_print_codes_read.f90#L49-L168) stops after `wetland_cs`. When `gwflow_wb` is listed, its daily, monthly, yearly, and average annual switches replace the corresponding `gwflow.input` water-balance settings ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L265-L311)). The daily water-balance switch also controls channel hydrograph-separation output.

`gwflow_obs` and `gwflow_solute` select their four output periods independently. `gwflow_heat` supports daily, yearly, and average annual output; its monthly column does not enable a monthly heat-balance output. If the heat or solute row is omitted, its periods follow the water-balance settings. If the observation row is omitted, its four period flags retain their default enabled values.

`gwflow_pump` is a group switch: any `y` among its four columns enables pumping output at all implemented periods; four `n` values disable the group. `gwflow_flux` is also a group switch: a `y` in its daily or yearly column enables its diagnostics; its monthly and average annual columns do not enable the group. These two rows do not independently select output periods.

On SWAT+ dev, `hru_cb` calls the legacy carbon writer once per enabled daily, monthly or yearly output event, and any column that is not `n` also triggers the end-of-simulation soil snapshot ([`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L529-L548)). `hru_cb_vars` calls the legacy carbon-variable writer for daily, monthly and yearly periods when `carbon = 2` in `codes.bsn` ([`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L550-L559)). Both rows accept `y` for normal output and `l` for the same output plus per-layer rows. The extra carbon diagnostic files are no longer turned on by `l`; use [cbn\_diag\_int](../../carbon/carbon.bsn/cbn_diag_int.md) in `carbon.bsn`. Neither row has an average-annual writer call, so the fourth column does not request an average-annual legacy report.
