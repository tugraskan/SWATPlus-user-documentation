---
description: >-
  The septic systems database summarizes parameters used by the model to
  simulate different types of Onsite Wastewater Systems.
---

# septic.sep

Information of water quality or effluent characteristics required to simulate different types of Onsite Wastewater Systems (OWSs) is stored in the septic water quality database. The information contained in the septic water quality database includes the septic tank effluent flow rate for per capita and the effluent characteristics of various septic systems. The database file distributed with SWAT+ includes water quality data for most conventional, advanced, and failing septic systems. It was developed based on the field data summarized by Siegrist et al. (2005), McCray et al. (2005), and OWTS 201 (2005).

| Field                 | Description                                                 | Type   | Unit  | Default | Range     |
| --------------------- | ----------------------------------------------------------- | ------ | ----- | ------- | --------- |
| [name](name_sepdb.md) | Septic record name (read but not used by the model) | string | ​n/a | ​n/a | n/a |
| [q\_rate](q_rate.md) | Per-capita septic tank effluent flow rate (read but not used by the model) | ​real | m^3/capita/d | 0.0 | 0.0-1.0 |
| [bod](bod.md) | ​7-day Biological Oxygen Demand of the septic tank effluent | ​real  | mg/l  | ​0.0    | 0.0-300.0 |
| [tss](tss.md) | Total suspended solids in the septic tank effluent          | ​real  | ​mg/l | ​0.0    | 0.0-300.0 |
| [nh4\_n](nh4_n.md) | ​Ammonium nitrogen in the septic tank effluent              | ​real  | ​mg/l | ​0.0    | ​         |
| [no3\_n](no3_n.md) | ​Nitrate nitrogen in the septic tank effluent               | ​real  | ​mg/l | 0.0     |           |
| [no2\_n](no2_n.md) | Nitrite nitrogen in the septic tank effluent                | real   | mg/l  | 0.0     |           |
| [org\_n](org_n.md) | Organic nitrogen in the septic tank effluent                | real   | mg/l  | 0.0     |           |
| [min\_p](min_p.md) | Mineral phosphorus in the septic tank effluent              | real   | mg/l  | 0.0     |           |
| [org\_p](org_p.md) | Organic phosphorus in the septic tank effluent              | real   | mg/l  | 0.0     |           |
| [fcoli](fcoli.md) | Fecal coliform concentration in the septic tank effluent | real | cfu/100 mL | 0.0 |  |

#### References

> Siegrist et al. (2005)&#x20;
>
> McCray et al. (2005)
>
> OWTS 201 (2005)
