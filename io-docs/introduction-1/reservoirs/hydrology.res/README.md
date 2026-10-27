---
description: This file contains the reservoir hydrology parameters.
---

# hydrology.res

| Field                  | Description                                                           |   Type  |  Unit | Default |    Range    |
| ---------------------- | --------------------------------------------------------------------- | :-----: | :---: | :-----: | :---------: |
| [name](name.md)        | Name of the reservoir hydrology record                                |  string |  n/a  |   n/a   |     n/a     |
| [yr\_op](yr_op.md) | The year of the simulation that the reservoir becomes operational     | integer |  n/a  |    1    |    1-9999   |
| [mon\_op](mon_op.md) | The month of the simulation that the reservoir becomes operational    | integer |  n/a  |    1    |     1-12    |
| [area\_ps](area_ps.md) | Reservoir surface area when reservoir is filled to principal spillway |   real  |   ha  |  1500.0 |   1-3000.0  |
| [vol\_ps](vol_ps.md) | Volume of water needed to fill the reservoir to principal spillway    |   real  |  ha-m |  1500.0 | 15.0-3000.0 |
| [area\_es](area_es.md) | Reservoir surface area when reservoir is filled to emergency spillway |   real  |   ha  |  500.0  |  1.0-1000.0 |
| [vol\_es](vol_es-1.md) | Volume of water needed to fill the reservoir to emergency spillway    |   real  |  ha-m |   55.0  |  10.0-100.0 |
| [k](k.md)              | Hydraulic conductivity of the reservoir bottom                        |   real  | mm/hr |   0.0   |   0.0-1.0   |
| [evap\_co](evap_co.md) | Reservoir evaporation coefficient                                     |   real  |  n/a  |   0.60  |   0.0-1.0   |
| [shp\_co1](shp_co1.md) | Lag parameter for smoothing reservoir outflow when outflow is increasing | real | n/a | 0.0 |  |
| [shp\_co2](sho_co2.md) | Lag parameter for smoothing reservoir outflow when outflow is decreasing or unchanged | real | n/a | 0.0 |  |
