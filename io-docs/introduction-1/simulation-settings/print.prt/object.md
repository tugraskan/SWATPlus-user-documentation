---
description: Objects that output can be printed for at different time steps
---

# object

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
| water\_allo     | Water allocation                                               |
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
| hyd             | Incoming and outgoing hydrographs                              |
| ru              | Routing unit output                                            |
| pest            | Pesticide output for all objects and basin                     |
| basin\_salt     |                                                                |
| hru\_salt       |                                                                |
| ru\_salt        |                                                                |
| aqu\_salt       |                                                                |
| channel\_salt   |                                                                |
| res\_salt       |                                                                |
| wetland\_salt   |                                                                |
| basin\_cs       |                                                                |
| hru\_cs         |                                                                |
| ru\_cs          |                                                                |
| aqu\_cs         |                                                                |
| channel\_cs     |                                                                |
| res\_cs         |                                                                |
| wetland\_cs     |                                                                |
| lsu\_cb\_gl | LSU-area-weighted carbon gain/loss |
| lsu\_cb\_trf | LSU-area-weighted carbon transformations |
| lsu\_cb\_plt | LSU-area-weighted plant carbon state |
| hru\_cb | Legacy carbon output switch retained for compatibility; no current writer uses it |
| hru\_cb\_vars | Legacy carbon-variable switch retained for compatibility; no current writer uses it |
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

GWFlow output rows require label-based object parsing: set use_obj_lbls to a value other than n. When gwflow_wb is listed, its daily, monthly, yearly, and average annual switches replace the corresponding gwflow.input water-balance settings. The daily water-balance switch also controls channel hydrograph-separation output.

gwflow_obs and gwflow_solute select their four output periods independently. gwflow_heat supports daily, yearly, and average annual output; its monthly column does not enable a monthly heat-balance output. If the heat or solute row is omitted, its periods follow the water-balance settings. If the observation row is omitted, its four period flags retain their default enabled values.

gwflow_pump is a group switch: any y among its four columns enables pumping output at all implemented periods; four n values disable the group. gwflow_flux is also a group switch: a y in its daily or yearly column enables its diagnostics; its monthly and average annual columns do not enable the group. These two rows do not independently select output periods.
