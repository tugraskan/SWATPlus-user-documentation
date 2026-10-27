---
description: This file controls the simulation of snowfall and snowmelt processes.
---

# snow.sno

| Field                      | Description                                       |  Type  |      Unit     | Default |   Range   |
| -------------------------- | ------------------------------------------------- | :----: | :-----------: | :-----: | :-------: |
| [name](name.md)            | Name of the snow record                           | string |      n/a      |   n/a   |    n/a    |
| [fall\_tmp](fall_tmp.md)   | Snowfall temperature                              |  real  |       ºC      |    1    |   -5 - 5  |
| [melt\_tmp](melt_tmp.md)   | Snow melt base temperature                        |  real  |       ºC      |   0.5   |   -5 - 5  |
| [melt\_max](melt_max.md)   | Melt factor for snow on June 21                   |  real  | mm H2O/day-ºC |   0.0   |  0.0-10.0 |
| [melt\_min](melt_min.md)   | Melt factor for snow on December 21               |  real  | mm H2O/day-ºC |   0.0   |  0.0-10.0 |
| [tmp\_lag](tmp_lag.md)     | Snowpack temperature lag factor                   |  real  |      none     |    1    |   0.01-1  |
| [snow\_h2o](snow_h2o.md) | Snow water content at full ground cover (100% snow cover) | real | mm | 0.0 | 0.0-500.0 |
| [cov50](cov50.md) | Fraction of snow_h2o at which snow cover is 50% | real | fraction | 0.50 | 0.0-1.0 |
| [snow\_init](snow_init.md) | Initial snow water content at start of simulation |  real  |       mm      |   0.0   |  0.0-0.50 |
