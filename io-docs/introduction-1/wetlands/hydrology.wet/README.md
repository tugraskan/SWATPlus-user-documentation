---
description: This file contains the wetland hydrology parameters.
---

# hydrology.wet

| Field                                    | Description                                                                       |  Type  |   Unit   | Default | Range |
| ---------------------------------------- | --------------------------------------------------------------------------------- | :----: | :------: | :-----: | :---: |
| [name](name.md)                          | Name of the wetland hydrology record                                              | string |    n/a   |   n/a   |  n/a  |
| [hru\_ps](hru_ps.md)                     | Fraction of HRU area at principal spillway (when surface inlet riser flow starts) |  real  |   frac   |    0    |       |
| [dp\_ps](dp_ps.md)                       | Average depth of water at principal spillway                                      |  real  |    mm    |    0    |       |
| [hru\_es](hru_es.md)                     | Fraction of HRU area at emergency spillway (when starts to spill into ditch)      |  real  |   frac   |    0    |       |
| [dp\_es](dp_es.md)                       | Average depth of water at emergency spillway                                      |  real  |    mm    |    0    |       |
| [k](k.md) | Hydraulic conductivity of the wetland bottom | real | mm/hr | 0.01 |  |
| [evap](evap.md)                          | Wetland evaporation coefficient                                                   |  real  |    n/a   |   0.70  |       |
| [vol\_area\_co](vol_area_co.md)          | Volume surface area coefficient for HRU impoundment                               |  real  |    n/a   |   1.0   |       |
| [vol\_dp\_a](vol_dp_a.md)                | Volume depth coefficient for HRU impoundment                                      |  real  |    n/a   |   1.0   |       |
| [vol\_dp\_b](vol_dp_b.md)                | Volume depth coefficient for HRU impoundment                                      |  real  |    n/a   |   1.0   |       |
| [hru\_frac](hru_frac.md) | Fraction of HRU that drains into wetland (read but not used by SWAT+ main (6f515368)) | real | fraction | 0.5 |  |
