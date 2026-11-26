---
description: This file contains the general physical and chemical aquifer properties.
---

# aquifer.aqu

[`aqu_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_read.f90#L30-L59) reads this file in free format, one record per aquifer. Each aquifer object in **aquifer.con** points to a record by ID. Daily aquifer water balance and nutrient calculations are in [`aqu_1d_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L106-L175).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [id](id-aquifer.aqu.md) | ID of the aquifer | integer | n/a |  |  |
| [name](name.md) | Name of the aquifer (not used in simulation) | string | n/a | n/a | n/a |
| [init](aqu_ini.md) | Pointer to the aquifer constituent initialization record in initial.aqu_cs | string | n/a | n/a | n/a |
| [gw_flo](gw_flo.md) | Initial groundwater flow | real | mm | 0.05 | 0-2 |
| [dep_bot](dep_bot.md) | Depth from mid-slope surface to bottom of aquifer | real | m | 10.0 | 0-10 |
| [dep_wt](dep_wt-1.md) | Depth from mid-slope surface to initial water table | real | m | 10.0 | 0-10 |
| [no3_n](no3_n.md) | Initial NO3-N concentration in aquifer | real | ppm NO3-N | 0 | 0-1000 |
| [sol_p](sol_p.md) | Mineral P concentration in aquifer (fixed) | real | mg P/L | 0 | 0-1000 |
| [carbon](ptl_n.md) | Organic carbon in aquifer (printed in aquifer output; not used in simulation calculations) | real | percent | 0.50 | 0-15 |
| [flo_dist](ptl_p.md) | Average flow distance to stream or object (not used in simulation calculations) | real | m | 50.0 | 0-1000 |
| [bf_max](flo_max.md) | Baseflow rate at which all streams linked to an aquifer receive groundwater flow | real | mm | 1.0 | 0-2 |
| [alpha_bf](alpha_bf.md) | Alpha factor for groundwater recession curve | real | 1/days | 0.05 | 0-1 |
| [revap](revap.md) | Groundwater revap coefficient | real | fraction | 0 | 0-1 |
| [rchg_dp](rchg_dp.md) | Fraction of aquifer recharge seeping to deep aquifer | real | fraction | 0 | 0-1 |
| [spec_yld](spec_yld.md) | Specific yield of the aquifer | real | m^3/m^3 | 0 | 0-0.40 |
| [hl_no3n](hl_no3n.md) | Half-life of NO3-N in the aquifer | real | days | 0 | 0-200 |
| [flo_min](flo_min.md) | Threshold depth from surface to water table for groundwater flow to occur | real | m | 3 | 0-10 |
| [revap_min](revap_min.md) | Threshold depth from surface to water table for revap to occur | real | m | 5 | 0-10 |
