---
description: "This file defines decision tables used to control flow-related actions."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file defines decision tables used to control flow-related actions.

# flo_con.dtl

The file contains a title, a decision-table count, and table definitions. Each table definition gives its condition, alternative, and action counts. Follow it with the condition rows and action rows; repeat alternative and outcome values according to the alternative count.

## Number of decision tables

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [mdtbl](mdtbl.md) | Number of decision tables | integer | n/a | — | — |

## Table definition

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Record name | string | n/a | — | — |
| [conds](conds.md) | Number of condition entries that follow for this decision table | integer | n/a | — | — |
| [alts](alts.md) | Number of alternative branches evaluated for each condition | integer | n/a | — | — |
| [acts](acts.md) | Number of action entries that follow for this decision table | integer | n/a | — | — |

## Conditions

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [var](var.md) | Condition variable being tested (e.g. volume, flow, sw, time) | string | n/a | — | — |
| [ob](ob.md) | Object type associated with the condition (e.g. res, hru, canal) | string | n/a | — | — |
| [ob_num](ob_num.md) | Numeric identifier of the object associated with the condition | integer | n/a | — | — |
| [lim_var](lim_var.md) | Limit variable compared against the condition variable (e.g. evol, pvol, fc, ul) | string | n/a | — | — |
| [lim_op](lim_op.md) | Operator applied when comparing the condition variable to the limit (one of *, +, -) | string | n/a | — | — |
| [lim_const](lim_const.md) | Constant value used with the limit operator in the condition comparison | real | — | — | — |
| [alt(ic,ial)](alt_ic_ial.md) | Alternative value for condition ic under alternative branch ial | string | n/a | — | — |

## Actions

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [typ](typ.md) | Type of action to perform (e.g. reservoir release, irrigate, fertilize) | string | n/a | — | — |
| [ob](ob_2.md) | Object type targeted by the action (e.g. res, hru, canal) | string | n/a | — | — |
| [ob_num](ob_num_2.md) | Numeric identifier of the object targeted by the action | integer | n/a | — | — |
| [name](name_2.md) | Record name | string | n/a | — | — |
| [option](option.md) | Action-specific option whose meaning depends on the action type (e.g. rate input | string | n/a | — | — |
| [const](const.md) | Primary constant for the action (e.g. rate or duration) | real | — | — | — |
| [const2](const2.md) | Secondary constant for the action (e.g. additional rate or duration parameter) | real | — | — | — |
| [file_pointer](file_pointer.md) | External file or equation pointer referenced by the action option (e.g. weir equation pointer) | string | n/a | — | — |
| [act_outcomes(iac,ial)](act_outcomes_iac_ial.md) | Outcome flag for action iac under alternative ial ("y" to perform the action, "n" to skip it) | string | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
