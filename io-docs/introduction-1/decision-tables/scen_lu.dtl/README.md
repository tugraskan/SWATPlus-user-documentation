---
description: "This file defines decision tables for land-use scenarios."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file defines decision tables for land-use scenarios.

# scen_lu.dtl

The file contains a title, a decision-table count, and table definitions. Each table definition gives its condition, alternative, and action counts. Follow it with the condition rows and action rows; repeat alternative and outcome values according to the alternative count.

## Number of decision tables

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [mdtbl](mdtbl.md) | Number of decision tables | integer | n/a | — | — |

## Table definition

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Record name | string | n/a | — | — |
| [conds](conds.md) | Number of condition entries that follow for this table | integer | n/a | — | — |
| [alts](alts.md) | Number of alternative condition sets evaluated for each condition | integer | n/a | — | — |
| [acts](acts.md) | Number of action entries that follow for this table | integer | n/a | — | — |

## Conditions

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [var](var.md) | Condition variable tested (e.g. volume, flow, sw, time) | string | n/a | — | — |
| [ob](ob.md) | Object type the condition applies to (e.g. res, hru, canal) | string | n/a | — | — |
| [ob_num](ob_num.md) | Numeric index of the object the condition applies to | integer | n/a | — | — |
| [lim_var](lim_var.md) | Limit variable compared against (e.g. evol, pvol, fc, ul) | string | n/a | — | — |
| [lim_op](lim_op.md) | Operator applied to the limit comparison (*, +, -) | string | n/a | — | — |
| [lim_const](lim_const.md) | Constant value used in the limit comparison | real | — | — | — |
| [alt(ic,ial)](alt_ic_ial.md) | Alternative value for condition ic under alternative set ial | string | n/a | — | — |

## Actions

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [typ](typ.md) | Type of action performed (e.g. reservoir release, irrigate, fertilize) | string | n/a | — | — |
| [ob](ob_2.md) | Object type the action applies to (e.g. res, hru, canal) | string | n/a | — | — |
| [ob_num](ob_num_2.md) | Numeric index of the object the action applies to | integer | n/a | — | — |
| [name](name_2.md) | Record name | string | n/a | — | — |
| [option](option.md) | Action option specific to its type (e.g. rate input, drawdown days, weir equation pointer) | string | n/a | — | — |
| [const](const.md) | Primary constant for the action (e.g. rate, days) | real | — | — | — |
| [const2](const2.md) | Secondary constant for the action (e.g. rate, days) | real | — | — | — |
| [file_pointer](file_pointer.md) | Pointer referencing an external option (e.g. weir equation pointer) | string | n/a | — | — |
| [act_outcomes(iac,ial)](act_outcomes_iac_ial.md) | Outcome flag for action iac under alternative ial ("y" performs the action, "n" does not) | string | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
