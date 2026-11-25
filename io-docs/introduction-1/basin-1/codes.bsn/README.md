---
description: This file contains control codes for the simulation of basin-level processes.
---

# codes.bsn

Control codes for basin-wide simulation options, read sequentially into `bsn_cc` by [`basin_read_cc.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_cc.f90#L16-L28).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [pet\_file](pet_file.md) | Currently not used | string |  |  |  |
| [wq\_file](wq_file.md) | Currently not used | string |  |  |  |
| [pet](pet.md) | Potential Evapotranspiration (PET) method (0 = Priestley-Taylor, 1 = Penman-Monteith, 2 = Hargreaves, 3 = read `pet.cli`) | integer |  |  |  |
| [event](event.md) | Extra input columns: 0 = off; any other value = the last column of plants.plt is read as the plant class, and soil\_plant.ini is read with a cs column | integer |  |  |  |
| [crack](crack.md) | Crack flow | integer |  |  |  |
| [swift\_out](swift_out.md) | Writing of input file for SWIFT | integer |  |  |  |
| [sed\_det](sed_det.md) | Peak runoff rate method | integer |  |  |  |
| [rte\_cha](rte_cha.md) | Channel routing | integer |  |  |  |
| [deg\_cha](deg_cha.md) | Currently not used | integer |  |  |  |
| [wq\_cha](wq_cha.md) | Currently not used | integer |  |  |  |
| [nostress](nostress.md) | Turning off of plant stress | integer |  |  |  |
| [cn](cn.md) | Currently not used | integer |  |  |  |
| [c\_fact](c_fact.md) | C-factor method selector (entered value overwritten with 1 before method selection in main 6f515368) | integer |  |  |  |
| [carbon](carbon.md) | Carbon routine (0 = static, 1 = C-FARM reserved/not implemented, 2 = Century/SWAT-C) | integer |  |  |  |
| [lapse](lapse.md) | Precipitation and temperature lapse rate control | integer |  |  |  |
| [uhyd](uhyd.md) | Unit Hydrograph method | integer |  |  |  |
| [sed\_cha](sed_cha.md) | Currently not used | integer |  |  |  |
| [tiledrain](tiledrain.md) | Tile drainage equation code | integer |  |  |  |
| [wtable](wtable.md) | Water table depth algorithms | integer |  |  |  |
| [soil\_p](soil_p.md) | Soil phosphorus model | integer |  |  |  |
| [gampt](gampt.md) | Surface runoff method | integer |  |  |  |
| [atmo\_dep](atmo_dep.md) | Currently not used | string |  |  |  |
| [stor\_max](stor_max.md) | Currently not used | integer |  |  |  |
| [qual2e](qual2e.md) | Instream nutrient routing method (0 = QUAL2E; 1 = QUAL2E plus simplified inorganic-to-organic transformation override) | integer |  |  |  |
| [gwflow](gwflow.md) | GWFlow module switch | integer |  |  |  |
| [idc\_till](idc_till.md) | Tillage method used when carbon = 2: 1 = DSSAT, 2 = EPIC, 3 = Kemanian (default), 4 = DNDC | integer |  |  |  |
