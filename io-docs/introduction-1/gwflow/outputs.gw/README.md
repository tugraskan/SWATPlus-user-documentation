---
description: "Observation cells for GWFlow output."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file selects cells for the [GWFlow observation reports](../../../swat+-output-files/gwflow-outputs/observation-wells.md). The reader also accepts two older record types that no longer produce output.

SWAT+ looks for `outputs.gw` in the simulation working directory; it is not selected through `file.cio`. See the [`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L575-L620) reader.

# outputs.gw

The first two lines are a title and column headings. Each following line has a record type and a value, in any order. Blank lines, lines with fewer than two values and unrecognized record types are skipped. Record types are case-sensitive ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L601-L619)).

## Observation cell

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [record_type](record_type.md) | `observation_cell` | string | n/a | — | — |
| [value](value_2.md) | Cell number to report | integer | n/a | — | 1 to ncell |

## Head output date

Older record type. The date is stored, but no output is written for it ([`gwflow_simulate.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_simulate.f90#L388-L393)).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [record_type](record_type.md) | `head_output_time` | string | n/a | — | — |
| [value](value.md) | Date as year × 1000 + day of year | integer | n/a | — | — |

## Detailed-output cell

Older record type. The cell number is stored, but no output uses it ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L616-L617)).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [record_type](record_type.md) | `detail_debug_cell` | string | n/a | — | — |
| [value](value_3.md) | Cell number; not used | integer | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
