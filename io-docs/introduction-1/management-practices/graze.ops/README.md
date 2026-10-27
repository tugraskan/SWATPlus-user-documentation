---
description: This file contains pre-defined grazing operations.
---

# graze.ops

This operation removes plant biomass at a specified rate and allows simultaneous application of manure.&#x20;

{% hint style="warning" %}
The parameter values of the pre-defined grazing operations are very rough estimates. If grazing is relevant in a watershed, the user should research their own values based on the stocking rate and type of animal.
{% endhint %}

| Field                      | Description                                                   |  Type  |     Unit    | Default |    Range   |
| -------------------------- | ------------------------------------------------------------- | :----: | :---------: | :-----: | :--------: |
| [name](name_graze.md)      | Grazing operation name                                        | string |     n/a     |   n/a   |     n/a    |
| [fert](fertnm.md) | Fertilizer database name for manure deposited during grazing | string | n/a | n/a | n/a |
| [bm\_eat](eat.md)          | Dry weight of biomass removed by grazing daily                |  real  | (kg/ha)/day |   0.0   |  0.0-500.0 |
| [bm\_tramp](tramp.md) | Currently not used | real | (kg/ha)/day | 0.0 | 0.0-500.0 |
| [man\_amt](manure.md)      | Dry weight of manure deposited daily                          |  real  | (kg/ha)/day |   0.0   |  0.0-500.0 |
| [grz\_bm\_min](bio_min.md) | Minimum plant biomass for grazing to occur                    |  real  |    kg/ha    |   0.0   | 0.0-5000.0 |

