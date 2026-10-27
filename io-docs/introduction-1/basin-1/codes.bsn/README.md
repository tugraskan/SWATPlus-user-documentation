---
description: This file contains control codes for the simulation of basin-level processes.
---

# codes.bsn

| Field                     | Description                                      | Type    |
| ------------------------- | ------------------------------------------------ | ------- |
| pet\_file\* | Currently not used                               | string  |
| wq\_file\* | Currently not used                               | string  |
| [pet](pet.md)             | Potential Evapotranspiration (PET) method        | integer |
| [event](event.md)\* | Extra input columns: 0 = off; any other value = the last column of plants.plt is read as the plant class, and soil\_plant.ini is read with a cs column | integer |
| [crack](crack.md)\* | Crack flow                                       | integer |
| [swift\_out](rtu_wq.md)   | Writing of input file for SWIFT                  | integer |
| [sed\_det](sed_det.md) | Peak runoff rate method | integer |
| [rte\_cha](rte_cha.md)\* | Channel routing                                  | integer |
| deg\_cha\* | Currently not used                               | integer |
| wq\_cha\* | Currently not used                               | integer |
| [nostress](rte_pest.md)   | Turning off of plant stress                      | integer |
| cn                        | Currently not used                               | integer |
| c\_fact\* | Currently not used                               | integer |
| [carbon](carbon.md)\* | Carbon routine                                   | integer |
| [lapse](baseflo.md)       | Precipitation and temperature lapse rate control | integer |
| [uhyd](uhyd.md)           | Unit Hydrograph method                           | integer |
| sed\_cha\* | Currently not used                               | integer |
| [tiledrain](tiledrain.md)\* | Tile drainage equation code                      | integer |
| [wtable](wtable.md)\* | Water table depth algorithms                     | integer |
| [soil\_p](soil_p.md)\* | Soil phosphorus model                            | integer |
| [gampt](abstr_init.md)    | Surface runoff method                            | integer |
| atmo\_dep\* | Currently not used                               | string  |
| stor\_max\* | Currently not used                               | integer |
| qual2e                    | Instream nutrient routing method                 | integer |
| [gwflow](headwater.md) | GWFlow module switch | integer |
| [idc\_till](idc_till.md)  | Tillage method used when carbon = 2: 1 = DSSAT, 2 = EPIC, 3 = Kemanian (default), 4 = DNDC | integer |

\* Input-file labels marked with an asterisk have different Fortran names: `pet_file` → `bsn_cc%petfile`; `wq_file` → `bsn_cc%wwqfile`; `event` → `bsn_cc%nam1`; `crack` → `bsn_cc%crk`; `rte_cha` → `bsn_cc%rte`; `deg_cha` → `bsn_cc%deg`; `wq_cha` → `bsn_cc%wq`; `c_fact` → `bsn_cc%cfac`; `carbon` → `bsn_cc%cswat`; `sed_cha` → `bsn_cc%sed_ch`; `tiledrain` → `bsn_cc%tdrn`; `wtable` → `bsn_cc%wtdn`; `soil_p` → `bsn_cc%sol_p_model`; `atmo_dep` → `bsn_cc%atmo`; `stor_max` → `bsn_cc%smax`. [Reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/basin_read_cc.f90#L24).
