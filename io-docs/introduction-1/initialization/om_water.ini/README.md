# om\_water.ini

| Field                  | Description                                |  Type  |     Unit    | Default | Range |
| ---------------------- | ------------------------------------------ | :----: | :---------: | :-----: | :---: |
| [name](name.md)\* | Name of water and nutrient initialization  | string |     n/a     |   n/a   |  n/a  |
| [vol](vol.md)\* | Volume of water | real | fraction | 0 |  |
| [sed](sed.md) | Sediment | real | ppm | 0 |  |
| [part\_n](part_n.md)\* | Organic N | real | ppm | 0 |  |
| [part\_p](part_p.md)\* | Organic P | real | ppm | 0 |  |
| [no3](no3.md) | NO3-N | real | ppm | 0 |  |
| [solp](solp.md) | Mineral (soluble P) | real | ppm | 0 |  |
| [chl\_a](chl_a.md)\* | Chlorophyll-a | real | ppm | 0 |  |
| [nh3](nh3.md) | NH3 | real | ppm | 0 |  |
| [no2](no2.md) | NO2 | real | ppm | 0 |  |
| [cbn\_bod](cbn_bod.md)\* | Carbonaceous biological oxygen demand | real | ppm | 0 |  |
| [dis\_ox](dis_ox.md)\* | Dissolved oxygen | real | ppm | 0 |  |
| [san](sand.md) | Detached sand | real | ppm | 0 |  |
| [sil](silt.md) | Detached silt | real | ppm | 0 |  |
| [cla](clay.md) | Detached clay | real | ppm | 0 |  |
| [sag](sm_ag.md) | Detached small aggregates | real | ppm | 0 |  |
| [lag](l_ag.md) | Detached large aggregates | real | ppm | 0 |  |
| [grv](gvl.md) | Gravel | real | ppm | 0 |  |
| [tmp](tmp.md)\* | Temperature                                |  real  |    deg C    |    0    |       |

\* Input-file labels marked with an asterisk have different Fortran names: `name` → `om_init_name(ichi)`; `vol` → `om_init_water(ichi)%flo`; `part_n` → `om_init_water(ichi)%orgn`; `part_p` → `om_init_water(ichi)%sedp`; `chl_a` → `om_init_water(ichi)%chla`; `cbn_bod` → `om_init_water(ichi)%cbod`; `dis_ox` → `om_init_water(ichi)%dox`; `tmp` → `om_init_water(ichi)%temp`. [Reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/om_water_init.f90#L54).
