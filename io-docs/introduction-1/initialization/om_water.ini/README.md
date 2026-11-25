---
description: >-
  This file defines initial water volume fractions, sediment concentrations,
  organic and mineral nutrient concentrations, and temperature for channels,
  reservoirs, and wetlands.
---

# om\_water.ini

[`om_water_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/om_water_init.f90#L29-L57) reads `om_water.ini` (listed on the `init` row of [**file.cio**](../../master-file-file.cio.md)). Records are referenced by `org_min` in [**initial.cha**](../../channels/initial.cha/) and [**initial.res**](../../reservoirs/initial.res/) (for both reservoirs and wetlands). After setting the initial water volume from `vol`, SWAT+ converts each input concentration (`ppm` = `mg/L` = `g/m^3`) into stored mass via [`res_convert_mass`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1285-L1306) for reservoirs/wetlands and [`hyd_convert_conc_to_mass`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1236-L1258) for SWAT-DEG channels.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Name of water and nutrient initialization | string | n/a | n/a | n/a |
| [vol](vol.md) | Volume of water | real | fraction | 0 |  |
| [sed](sed.md) | Sediment | real | ppm | 0 |  |
| [part\_n](part_n.md) | Organic N | real | ppm | 0 |  |
| [part\_p](part_p.md) | Organic P | real | ppm | 0 |  |
| [no3](no3.md) | NO3-N | real | ppm | 0 |  |
| [solp](solp.md) | Mineral (soluble P) | real | ppm | 0 |  |
| [chl\_a](chl_a.md) | Chlorophyll-a | real | ppm | 0 |  |
| [nh3](nh3.md) | NH3 | real | ppm | 0 |  |
| [no2](no2.md) | NO2 | real | ppm | 0 |  |
| [cbn\_bod](cbn_bod.md) | Carbonaceous biological oxygen demand | real | ppm | 0 |  |
| [dis\_ox](dis_ox.md) | Dissolved oxygen | real | ppm | 0 |  |
| [san](sand.md) | Detached sand | real | ppm | 0 |  |
| [sil](silt.md) | Detached silt | real | ppm | 0 |  |
| [cla](clay.md) | Detached clay | real | ppm | 0 |  |
| [sag](sm_ag.md) | Detached small aggregates | real | ppm | 0 |  |
| [lag](l_ag.md) | Detached large aggregates | real | ppm | 0 |  |
| [grv](gvl.md) | Gravel | real | ppm | 0 |  |
| [tmp](tmp.md) | Temperature | real | deg C | 0 |  |
