---
description: This file is used to schedule management operations.
---

# management.sch

Management operations can be scheduled by calendar date, by accumulated heat-unit fraction, or automatically using Decision Tables, as read by [`mgt_read_mgtops.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_mgtops.f90#L60-L92) and [`read_mgtops.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/read_mgtops.f90#L26-L33).

Each schedule block begins with a header line (`name`, `numb_ops`, `numb_auto`), followed first by `numb_auto` decision-table lines (`auto_name`, plus optional `auto_crop` tokens for generic rotation tables `pl_hv_summer1`, `pl_hv_winter1`, and `pl_hv_summer2`), and then by `numb_ops` scheduled operation lines (`op_typ`, `mon`, `day`, `hu_sch`, `op_data1`, `op_data2`, `op_data3`) in chronological order. Scheduled operations trigger when the current date matches `mon`/`day` ([`mgt_operatn.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operatn.f90#L49-L62)) or when `hu_sch > 0` and accumulated heat units exceed `hu_sch` ([`mgt_operatn.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operatn.f90#L64-L85)). Both automatic and scheduled operations may be used in the same schedule, with automatic decision-table lines listed first.

## Schedule header

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name-management.sch.md) | Name of the management schedule | string | n/a | n/a | n/a |
| [numb\_ops](numb_ops.md) | Number of scheduled management operations | integer | n/a | 0 | >= 0 |
| [numb\_auto](numb_auto.md) | Number of automatic operations (decision tables) | integer | n/a | 0 | >= 0 |

## Automatic operations (decision tables)

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [auto\_name](auto_name.md) | Name of the decision table in `lum.dtl` | string | n/a | n/a | n/a |
| [auto\_crop](auto_crop.md) | Optional crop name(s) for generic `pl_hv_*` decision tables | string | n/a | n/a | n/a |

## Scheduled operations

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [op\_typ](op_typ.md) | Type of management operation | string | n/a | n/a | n/a |
| [mon](mon.md) | Month operation is scheduled for | integer | n/a | 0 | 1-12 |
| [day](day.md) | Day of month operation is scheduled for | integer | n/a | 0 | 1-31 |
| [hu\_sch](hu_sch.md) | Heat-unit scheduling threshold fraction | real | fraction | 0.0 | >= 0.0 |
| [op\_data1](op_data1.md) | Operation data 1 (`op_char`) | string | n/a | n/a | n/a |
| [op\_data2](op_data2.md) | Operation data 2 (`op_plant`) | string | n/a | n/a | n/a |
| [op\_data3](op_data3.md) | Operation data 3 (`op3`) | real | varies | 0.0 | varies |
