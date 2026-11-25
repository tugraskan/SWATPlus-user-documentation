---
description: Regional plant-growth soft-calibration targets by crop or plant name.
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

Supplies regional average annual plant-growth soft-calibration targets, read into `plcal` ([`calibration_data_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L279)) by [`pl_read_regions_cal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_read_regions_cal.f90#L38-L99).

# plant\_gro.sft

After the title, region count, and headings, enter each region definition and its HRU element list, followed by `lum_num` plant-growth target rows.

## Region count

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [mreg](mreg.md) | Number of plant soft-calibration regions | integer | — | — | > 0 |

## Regions

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Region name (parsed but unused) | string | — | `default` | — |
| [lum\_num](lum_num.md) | Number of plant or land-use records in the region | integer | — | 0 | > 0 |
| [nspu](nspu.md) | Number of HRU element-list tokens on the region row | integer | — | 0 | >= 0 |
| [elem\_cnt](elem_cnt.md) | HRU indices or ranges (`-`) included in the region | integer | — | — | — |

## Plant-growth targets

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name_2.md) | Plant name matched against simulated plants in the region | string | — | `default` | — |
| [yield](yield.md) | Target average annual crop yield | real | t/ha | 0 | >= 0 |
| [npp](npp.md) | Target net primary productivity (parsed but unused) | real | t/ha | 0 | — |
| [lai\_mx](lai_mx.md) | Target maximum leaf area index (parsed but unused) | real | m2/m2 | 0 | — |
| [wstress](wstress.md) | Target water drought stress sum (parsed but unused) | real | — | 0 | — |
| [astress](astress.md) | Target water aeration stress sum (parsed but unused) | real | — | 0 | — |
| [tstress](tstress.md) | Target temperature stress sum (parsed but unused) | real | — | 0 | — |

In SWAT+ main (`6f515368`), [`calsoft_plant.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_plant.f90#L49-L516) calibrates `epco`, `pest_stress`, `lai_pot`, and `harv_idx` strictly against `yield`; `npp`, `lai_mx`, `wstress`, `astress`, and `tstress` are not used.
