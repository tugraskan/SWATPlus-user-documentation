---
description: This file controls the channel hydrology and sediment properties.
---

# hyd-sed-lte.cha

| Field                      | Description                                                   |  Type  |   Unit   |        Default       | Range |
| -------------------------- | ------------------------------------------------------------- | :----: | :------: | :------------------: | :---: |
| [name](name.md)            | Name of the channel hydrology and sediment record             | string |    n/a   |          n/a         |  n/a  |
| [order](order.md)          | Channel (stream) order; used by the channel sediment routine and by decision tables | integer |    n/a   |                      |       |
| [wd](wd.md) | Channel width                                                 |  real  |     m    | calculated by QSWAT+ |       |
| [dp](dp.md) | Channel depth                                                 |  real  |     m    | calculated by QSWAT+ |       |
| [slp](slp.md) | Channel slope                                                 |  real  |    m/m   | calculated by QSWAT+ |       |
| [len](len.md) | Channel length                                                |  real  |    km    | calculated by QSWAT+ |       |
| [mann](mann.md) | Channel Manning's n value                                     |  real  |   none   |         0.05         |       |
| [k](k.md) | Effective hydraulic conductivity of the channel alluvium      |  real  |   mm/h   |          1.0         |       |
| [erod\_fact](erod_fact.md) | Bank erosion exponent (currently not used) | real | none | 0.01 |  |
| [cov\_fact](cov_fact.md) | Channel cover factor                                          |  real  |   none   |         0.01         |  0-1  |
| [sinu](wd_rto.md)          | Channel sinuosity                                             |  real  |   none   |          6.0         |       |
| [eq\_slp](eq_slp.md) | Critical velocity multiplier | real | none | 0 |  |
| [d50](d50.md) | Channel median sediment size (input currently reset to 1.0) | real | mm | 12.0 |  |
| [clay](clay.md) | Clay content of channel bank and bed                          |  real  |     %    |         50.00        | 0-100 |
| [carbon](carbon.md)        | Carbon content of channel bank and bed                        |  real  |     %    |           0          | 0-100 |
| [dry\_bd](dry_bd.md) | Dry bulk density of the channel                               |  real  |   t/m3   |           0          |       |
| [side\_slp](side_slp.md) | Channel side-slope ratio | real | none | 0.50 |  |
| [bankfull\_flo](bankfull_flo.md) | Bankfull flow factor (currently reset to 1.5 by the model) |  real  |   none   |                      |       |
| [fps](fps.md)              | Floodplain slope                                              |  real  |    m/m   |         10.0         |       |
| [fpn](fpn.md)              | Floodplain Manning's n                                        |  real  |   none   |                      |       |
| [n\_conc](hc_erod.md) | Nitrogen concentration in channel bank and bed | real | mg/kg | 0.10 |  |
| [p\_conc](hc_ht.md) | Phosphorus concentration in channel bank and bed | real | mg/kg | 0.30 |  |
| [p\_bio](hc_len.md) | Fraction of phosphorus in channel bank and bed that is bioavailable | real | fraction | 0.30 |  |
