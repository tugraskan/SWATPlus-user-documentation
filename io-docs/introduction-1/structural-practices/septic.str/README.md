---
description: This file contains the septic system parameters.
---

# septic.str

Data contained in the septic.str data file are: type of septic system, geometry of biozone, characteristics of biomass, and bio-physical reaction coefficients occurring in the biozone (adapted from Siegrist et al. (2005)).

| Field                          | Description                                                                                                 | Type    | Unit         | Default | Range    |
| ------------------------------ | ----------------------------------------------------------------------------------------------------------- | ------- | ------------ | ------- | -------- |
| [name](name_sepdb.md)          | Name of septic system record                                                                                | string  | n/a          | n/a     | n/a      |
| [typ](typ.md) | 1-based septic water-quality record number in septic.sep | integer | n/a | 0 |  |
| [yr](yr.md)                    | ​Year the septic system became operational                                                                  | integer | n/a          | 0       |          |
| [operation](operation.md)\* | ​Septic system operation flag                                                                               | integer | n/a          | 0       | 0-2      |
| [residents](residents.md)\* | Number of permanent residents in the house (read but not used by the model) | real | n/a | 1 | 1.0-12.0 |
| [area](area.md) | Average drainfield area per septic system (read but not used by the model) | real | m^2 | 1 |  |
| [t\_fail](t_fail.md)\* | Time until failing systems gets fixed                                                                       | integer | days         | 0       | 0-150    |
| [dp\_bioz](dp_bioz.md)\* | Depth to the top of the biozone layer from the ground surface                                               | real    | mm           | 1       |          |
| [thk\_bioz](thk_bioz.md)\* | Thickness of biozone layer                                                                                  | real    | mm           | 1       |          |
| [cha\_dist](cha_dist.md)\* | Distance from septic system to the stream (read but not used by the model) | real | km | 2 |  |
| [sep\_dens](sep_dens.md)\* | Number of septic systems per square kilometer (read but not used by the model) | real | n/a | 2 |  |
| [bm\_dens](bm_dens.md)\* | Density of biomass                                                                                          | real    | kg/m^3       | 1       |          |
| [bod\_decay](bod_decay.md)\* | BOD decay rate coefficient                                                                                  | real    | m^3/day      | 2       |          |
| [bod\_conv](bod_conv.md)       | Conversion factor representing the proportion of mass bacterial growth and mass BOD degraded in the septic  | real    | n/a          | 2       |          |
| [fc\_lin](fc_lin.md)\* | Linear coefficient for calculation of field capacity in the biozone                                         | real    | n/a          | 1       |          |
| [fc\_exp](fc_exp.md)\* | Exponential coefficient for calculation of field capacity in the biozone                                    | real    | n/a          | 2       |          |
| [fecal\_decay](fecal_decay.md)\* | Fecal coliform bacteria decay rate coefficient | real | m^3/day | 2 |  |
| [tds\_conv](tds_conv.md)\* | Conversion factor for plaque from TDS                                                                       | real    | n/a          | 2       |          |
| [mort](mort.md)\* | Mortality rate coefficient                                                                                  | real    | n/a          | 2       |          |
| [resp](resp.md)\* | Respiration rate coefficient                                                                                | real    | n/a          | 3       |          |
| [slough1](slough1.md)\* | Linear coefficient for calculating the rate of biomass sloughing                                            | real    | n/a          | 2       |          |
| [slough2](slough2.md)\* | Exponential coefficient for calculating the rate of biomass sloughing                                       | real    | n/a          | 2       |          |
| [nit](nit.md)\* | Nitrification rate coefficient                                                                              | real    | n/a          | 2       |          |
| [denit](denit.md)\* | Denitrification rate coefficient                                                                            | real    | n/a          | 3       |          |
| [p\_sorp](p_sorp.md)\* | Linear P sorption distribution coefficient                                                                  | real    | L/kg         | 1       |          |
| [p\_sorp\_max](p_sorp_max.md)\* | Maximum P sorption capacity                                                                                 | real    | mg P/kg soil | 1       |          |
| [solp\_slp](solp_slp.md)\* | Slope of the linear effluent soluble P equation                                                             | real    | n/a          | 3       |          |
| [solp\_int](solp_init.md)\* | Intercept of the linear effluent soluble P equation                                                         | real    | n/a          | 3       |          |

\* Input-file labels marked with an asterisk have different Fortran names: `operation` → `sep(isep)%opt`; `residents` → `sep(isep)%cap`; `t_fail` → `sep(isep)%tfail`; `dp_bioz` → `sep(isep)%z`; `thk_bioz` → `sep(isep)%thk`; `cha_dist` → `sep(isep)%strm_dist`; `sep_dens` → `sep(isep)%density`; `bm_dens` → `sep(isep)%bd`; `bod_decay` → `sep(isep)%bod_dc`; `fc_lin` → `sep(isep)%fc1`; `fc_exp` → `sep(isep)%fc2`; `fecal_decay` → `sep(isep)%fecal`; `tds_conv` → `sep(isep)%plq`; `mort` → `sep(isep)%mrt`; `resp` → `sep(isep)%rsp`; `slough1` → `sep(isep)%slg1`; `slough2` → `sep(isep)%slg2`; `nit` → `sep(isep)%nitr`; `denit` → `sep(isep)%denitr`; `p_sorp` → `sep(isep)%pdistrb`; `p_sorp_max` → `sep(isep)%psorpmax`; `solp_slp` → `sep(isep)%solpslp`; `solp_int` → `sep(isep)%solpintc`. [Reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/sep_read.f90#L43).

#### References

> Siegrist, R.L., J. McCray, L. Weintraub, C. Chen, J. Bagdol, P. Lemonds, S. Van Cuyk, K. Lowe, R. Goldstein, and J. Rada (2005): Quantifying Site-Scale Processes and Watershed-Scale Cumulative Effects of Decentralized Wastewater Systems. Project No. WU-HT-00-27. Prepared for the National Decentralized Water Resources Capacity Development Project, Washington University, St. Louis, MO, by the Colorado School of Mines.
