---
description: These files contain the Decision Tables.
---

# lum.dtl

Line 1 is the title. Line 2 starts with the number of decision tables. Leave line 3 blank. For each table, enter a header and the definition row, then a condition header and exactly `conds` condition rows, then an action header and exactly `acts` action rows. Each condition row ends with `alts` comparison entries. Each action row ends with `alts` outcomes in the same order. Blank lines between table blocks are optional. [`dtbl_lum_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dtbl_lum_read.f90#L44-L99)

Management schedules name these tables as automatic operations, and each is evaluated daily for the HRU. Every action row that succeeds restarts its own `days_act` counter at 1 and, for most operations, clears the counter of the row immediately above it. [`hru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L183-L220) · [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L360-L362)

## Number of decision tables

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [mdtbl](mdtbl.md) | Number of decision tables | integer | n/a |  |  |

## Table definition

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](table_name.md) | Name of the decision table | string |  |  |  |
| [conds](conds.md) | Number of conditions | integer |  |  |  |
| [alts](alts.md) | Number of alternatives | integer |  |  |  |
| [acts](acts.md) | Number of actions | integer |  |  |  |

## Conditions

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [var](var.md) | Condition variable | string |  |  |  |
| [obj](obj.md) | Object type | string |  |  |  |
| [obj_num](obj_num.md) | Object index or condition-specific numeric input | integer |  |  |  |
| [lim_var](lim_var.md) | Limit variable | string |  |  |  |
| [lim_op](lim_op.md) | Arithmetic operator for building a threshold where the condition uses one | string |  |  |  |
| [lim_const](lim_const.md) | Limit constant | real |  |  |  |
| [alt](alt.md) | Comparison token, repeated once per alternative | string |  |  |  |

For `prob_unif`, enter the [application fraction](frac_app.md) in the second position, then the first day, limit placeholder, limit operator placeholder, last day, and the comparison tokens. For example, `prob_unif 0.3 121 null - 181 =` uses a probability of 0.3 and the two entered day bounds.

## Actions

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [act\_typ](act_typ.md) | Type of action | string |  |  |  |
| [obj](obj-1.md) | Object type | string |  |  |  |
| [obj\_num](obj_num-1.md) | Object index or other integer input for the action | integer |  |  |  |
| [name](name.md) | Action name | string |  |  |  |
| [option](option.md) | Action option | string |  |  |  |
| [const](const.md) | Action constant | real |  |  |  |
| [const2](const2.md) | Action constant | real |  |  |  |
| [fp](fp.md) | File pointer for action option | string |  |  |  |
| [outcome](outcome.md) | Action outcome token, repeated once per alternative | string |  |  |  |
