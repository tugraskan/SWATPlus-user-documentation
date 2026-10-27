---
description: This file controls the channel nutrient properties.
---

# nutrients.cha

| Field                                       | Description                                                                                            |   Type  |              Unit             | Default |    Range    |
| ------------------------------------------- | ------------------------------------------------------------------------------------------------------ | :-----: | :---------------------------: | :-----: | :---------: |
| [name](name.md)                             | Name of the channel nutrient record                                                                    |  string |              n/a              |   n/a   |     n/a     |
| <p><a href="plt_n.md">plt_n</a></p><p></p> | Channel organic N concentration SWAT+ main (6f515368) reads this value but does not use it in a calculation. | real | ppm | 0.0 | 0.0-100.0 |
| [ptl\_p](plt_p.md) | Channel organic P concentration SWAT+ main (6f515368) reads this value but does not use it in a calculation. | real | ppm | 0.0 | 0.0-100.0 |
| [alg\_stl](alg_stl.md) | Local algal settling rate in the channel at 20ºC | real | m/day | 1.0 | 0.15-1.82 |
| [ben\_disp](ben_disp.md) | Benthic source rate for dissolved P in the channel at 20ºC | real | mg P/m2*day | 0.05 | 0.001-0.10 |
| [ben\_nh3n](ben_nh3n.md) | Benthic source rate for NH3-N in the channel at 20ºC | real | mg N/m2*day | 0.50 | 0.0-1.0 |
| [ptln\_stl](ptln_stl.md) | Organic N settling rate in the channel at 20ºC | real | 1/day | 0.05 | 0.001-0.1 |
| [ptlp\_stl](ptlp_stl.md) | Organic P settling rate in the channel at 20ºC | real | 1/day | 0.05 | 0.001-0.10 |
| [cst\_stl](cst_stl.md) | Arbitrary non-conservative constituent settling rate in the channel at 20ºC SWAT+ main (6f515368) reads this value and allows calibration/default handling, but does not use it in channel water-quality routing. | real | 1/day | 2.50 | 0.01-10.0 |
| [ben\_cst](ben_cst.md) | Benthic source rate for arbitrary non-conservative constituents in the channel at 20ºC SWAT+ main (6f515368) reads this value and allows calibration/default handling, but does not use it in channel water-quality routing. | real | mg /m^2\*day | 2.50 | 0.01-10.0 |
| [cbn\_bod\_co](cbn_bod_co.md) | Carbonaceous biological oxygen demand deoxygenation rate in the channel at 20ºC | real | 1/day | 1.71 | 0.02-3.40 |
| [air\_rt](air_rt.md) | Reaeration rate in accordance with Fickian diffusion in the channel at 20ºC | real | 1/day | 50.0 | 0.0-100.0 |
| [cbn\_bod\_stl](cbn_bod_stl.md) | Rate of loss of CBOD due to settling in the channel at 20ºC | real | 1/day | 0.36 | -0.36-0.36 |
| [ben\_bod](ben_bod.md) | Sediment oxygen demand rate in the channel at 20ºC | real | mg O2/m2*day | 2.0 | 0.0-100.0 |
| [bact\_die](bact_die.md) | Coliform die-off rate in the channel at 20ºC SWAT+ main (6f515368) reads this value and may replace a nonpositive value with its default, but does not otherwise use it in a calculation. | real | 1/day | 2.0 | 0.05-4.0 |
| [cst\_decay  ](cst_decay.md) | Decay rate for arbitrary non-conservative constituents in the channel at 20ºC SWAT+ main (6f515368) reads this value and allows calibration/default handling, but does not use it in channel water-quality routing. | real | 1/day | 1.71 | 0.0-10.0 |
| [nh3n\_no2n](nh3n_no2n.md) | Biological oxidation rate of NH3 to NO2 in the channel at 20ºC in well-aerated conditions | real | 1/day | 0.55 | 0.10-1.0 |
| [no2n\_no3n](no2n_no3n.md) | Biological oxidation rate of NO2 to NO3 in the channel at 20ºC in well-aerated conditions | real | 1/day | 1.10 | 0.20-2.0 |
| [ptln\_nh3n](ptln_nh3n.md) | Hydrolysis rate of organic N to ammonia in the channel at 20ºC | real | 1/day | 0.21 | 0.20-0.40 |
| [ptlp\_solp](ptlp_solp.md) | Mineralization rate of organic P to dissolved P in the channel at 20ºC | real | 1/day | 0.35 | 0.01-0.70 |
| [q2e\_lt](q2e_lt.md) | Qual2E light averaging option                                                                          |   real  |              n/a              |    2    |     1-4     |
| [q2e\_alg](q2e_alg.md) | Qual2E option for calculating the local specific growth rate of algae                                  | integer |              n/a              |    2    |     1-3     |
| [chla\_alg](chla_alg.md) | Ratio of chlorophyll-a to algal biomass                                                                |   real  |         μg chla/mg alg        |   50.0  |  10.0-100.0 |
| [alg\_n](alg_n.md) | Fraction of algal biomass that is N                                                                    |   real  |          mg N/mg alg          |   0.08  |  0.07-0.09  |
| [alg\_p](alg_p.md) | Fraction of algal biomass that is P                                                                    |   real  |          mg P/mg alg          |   0.02  |  0.01-0.02  |
| [alg\_o2\_prod](alg_o2_prod.md) | Oxygen production rate per unit of algal photosynthesis                                                |   real  |          mg O2/mg alg         |   1.60  |  1.40-1.80  |
| [alg\_o2\_resp](alg_o2_resp.md) | Oxygen uptake rate per unit of algae respiration                                                       |   real  |          mg O2/mg alg         |   2.0   |  1.60-2.30  |
| [o2\_nh3n](o2_nh3n.md) | Oxygen uptake rate per unit of NH3-N oxidation                                                         |   real  |           mg O2/mg N          |   3.50  |  3.00-4.00  |
| [o2\_no2n](o2_no2n.md) | Oxygen uptake rate per unit of NO2-N oxidation                                                         |   real  |           mg O2/mg N          |   1.07  |  1.00-1.40  |
| [alg\_grow](alg_grow.md) | Maximum specific algal growth rate at 20ºC | real | 1/day | 2.0 | 1.00-3.00 |
| [alg\_resp](alg_resp.md) | Algal respiration rate at 20ºC | real | 1/day | 2.50 | 0.05-5.0 |
| [slr\_act](slr_act.md) | Fraction of solar radiation computed in the temperature heat balance that is photosynthetically active |   real  |            fraction           |   0.30  |   0.0-1.0   |
| [lt\_co](lt_co.md) | Half-saturation coefficient for light | real | kJ/(m^2*min) | 0.75 | 0.223-1.135 |
| [const\_n](const_n.md) | Michaelis-Menton half-saturation constant for N                                                        |   real  |             mg N/L            |   0.02  |  0.01-0.30  |
| [const\_p](const_p.md) | Michaelis-Menton half saturation constant for P                                                        |   real  |             mg P/L            |   0.03  |  0.001-0.05 |
| [lt\_nonalg](lt_nonalg.md) | Non-algal portion of the light extinction coefficient                                                  |   real  |              1/m              |   1.0   |   0.0-10.0  |
| [alg\_shd\_l](alg_shd_l.md) | Linear algal self-shading coefficient                                                                  |   real  |        1/(m\*ug chla/L)       |   0.03  | 0.006-0.065 |
| [alg\_shd\_nl](alg_shd_nl.md) | Nonlinear algal self-shading coefficient                                                               |   real  |    (1/m)(ug chla/L)^(-2/3)    |   0.05  |   0.0-1.0   |
| [nh3\_pref](nh3_pref.md) | Algal preference factor for ammonia                                                                    |   real  |              none             |   0.50  |   0.0-1.0   |
