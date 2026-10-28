---
description: "This file supplies regional plant-growth targets for soft calibration."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies regional plant-growth targets for soft calibration.

# plant_gro.sft

After the title, region count, and headings, enter each region definition and its element list. Follow it with the plant-growth targets for each of that region’s land uses.

## Region count

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [mreg](mreg.md) | Number of regions | integer | n/a | — | — |

## Regions

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Record name | string | n/a | — | — |
| [lum_num](lum_num.md) | Number of land uses defined within this region | integer | n/a | — | — |
| [nspu](nspu.md) | Number of element-list entries | integer | n/a | — | — |
| [elem_cnt](elem_cnt.md) | Element-list entry | integer | n/a | — | — |

## Plant-growth targets

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name_2.md) | Record name | string | n/a | — | — |
| [yield](yield.md) | Crop yield value used as a soft annual calibration target | real | — | — | — |
| [npp](npp.md) | Net primary productivity (biomass dry weight) value used as a soft annual calibration target | real | — | — | — |
| [lai_mx](lai_mx.md) | Maximum leaf area index value used as a soft annual calibration target | real | — | — | — |
| [wstress](wstress.md) | Sum of water (drought) stress value used as a soft annual calibration target | real | — | — | — |
| [astress](astress.md) | Sum of water (aeration) stress value used as a soft annual calibration target | real | — | — | — |
| [tstress](tstress.md) | Sum of temperature stress value used as a soft annual calibration target | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
