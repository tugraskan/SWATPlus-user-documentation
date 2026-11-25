---
description: Regional stream-order channel sediment targets for soft calibration.
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

Supplies regional stream-order channel sediment budget targets for soft calibration, read into `chcal` ([`calibration_data_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L318)) by [`ch_read_orders_cal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_orders_cal.f90#L40-L122).

# ch\_sed\_budget.sft

## Number of regions

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [mreg](mreg.md) | Number of channel soft-calibration regions | integer | — | — | > 0 |

## Region and channel elements

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Region name (parsed but unused) | string | — | `default` | — |
| [ord\_num](ord_num.md) | Number of stream orders defined for this region | integer | — | 0 | >= 0 |
| [nspu](nspu.md) | Number of element-list tokens on the region row | integer | — | 0 | >= 0 |
| [elem\_cnt](elem_cnt.md) | Channel indices or ranges (`-`) included in the region | integer | — | — | — |

## Stream-order targets

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name_2.md) | Stream-order or basin record name (`basin` enables output accumulation) | string | — | `""` | — |
| [chw](chw.md) | Target channel widening rate (parsed but unused) | real | mm/yr | 0 | — |
| [chd](chd.md) | Target channel downcutting or accretion rate (parsed but unused) | real | mm/yr | 0 | — |
| [hc](hc.md) | Target headcut advance rate (parsed but unused) | real | m/yr | 0 | — |
| [fpd](fpd.md) | Target flood-plain accretion rate (parsed but unused) | real | mm/yr | 0 | — |

In SWAT+ main (`6f515368`), setting `chsed = "y"` in `codes.sft` accumulates length-weighted simulated channel widening, downcutting, and headcut averages in [`calsoft_sum_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_sum_output.f90#L152-L182) and writes `hru-new.cal` entries in [`calsoft_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_control.f90#L108-L159), but no routine adjusts channel erodibility (`chcal%ord%prm%erod`) against `chw`, `chd`, `hc`, or `fpd`.
