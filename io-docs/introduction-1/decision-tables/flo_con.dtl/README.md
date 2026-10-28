---
description: "Defines flow decision tables that evaluate condition variables (such as volume, flow, or time) against limit operators and constants, then select among alternative action outcomes for flow-related objects."
---

# flo_con.dtl

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines flow decision tables that evaluate condition variables (such as volume, flow, or time) against limit operators and constants, then select among alternative action outcomes for flow-related objects.

The reader obtains the filename through `in_cond%dtbl_flo`.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record.

### Record at line 34

Source condition/loop: `if (.not. i_exist .or. in_cond%dtbl_flo == "null") then / else > do`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [mdtbl](mdtbl.md) | total number of flow decision tables defined in the file | integer | n/a | — | — |

### Record at line 43

Source condition/loop: `if (.not. i_exist .or. in_cond%dtbl_flo == "null") then / else > do > do i = 1, mdtbl`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | identifier of the decision table, referenced by flow objects to select this table | string | n/a | — | — |
| [conds](conds.md) | number of condition entries that follow for this decision table | integer | n/a | — | — |
| [alts](alts.md) | number of alternative branches evaluated for each condition | integer | n/a | — | — |
| [acts](acts.md) | number of action entries that follow for this decision table | integer | n/a | — | — |

### Record at line 57

Source condition/loop: `if (.not. i_exist .or. in_cond%dtbl_flo == "null") then / else > do > do i = 1, mdtbl > do ic = 1, dtbl_flo(i)%conds`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [var](var.md) | condition variable being tested (e.g. volume, flow, sw, time) | string | n/a | — | — |
| [ob](ob.md) | object type associated with the condition (e.g. res, hru, canal) | string | n/a | — | — |
| [ob_num](ob_num.md) | numeric identifier of the object associated with the condition | integer | n/a | — | — |
| [lim_var](lim_var.md) | limit variable compared against the condition variable (e.g. evol, pvol, fc, ul) | string | n/a | — | — |
| [lim_op](lim_op.md) | operator applied when comparing the condition variable to the limit (one of *, +, -) | string | n/a | — | — |
| [lim_const](lim_const.md) | constant value used with the limit operator in the condition comparison | real | — | — | — |
| [alt(ic,ial)](alt_ic_ial.md) | alternative value for condition ic under alternative branch ial | string | n/a | — | — |

### Record at line 65

Source condition/loop: `if (.not. i_exist .or. in_cond%dtbl_flo == "null") then / else > do > do i = 1, mdtbl > do iac = 1, dtbl_flo(i)%acts`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [typ](typ.md) | type of action to perform (e.g. reservoir release, irrigate, fertilize) | string | n/a | — | — |
| [ob](ob_2.md) | object type targeted by the action (e.g. res, hru, canal) | string | n/a | — | — |
| [ob_num](ob_num_2.md) | numeric identifier of the object targeted by the action | integer | n/a | — | — |
| [name](name_2.md) | name of the action within the decision table | string | n/a | — | — |
| [option](option.md) | action-specific option whose meaning depends on the action type (e.g. rate input, drawdown days, weir equation pointer) | string | n/a | — | — |
| [const](const.md) | primary constant for the action (e.g. rate or duration) | real | — | — | — |
| [const2](const2.md) | secondary constant for the action (e.g. additional rate or duration parameter) | real | — | — | — |
| [file_pointer](file_pointer.md) | external file or equation pointer referenced by the action option (e.g. weir equation pointer) | string | n/a | — | — |
| [act_outcomes(iac,ial)](act_outcomes_iac_ial.md) | outcome flag for action iac under alternative ial ("y" to perform the action, "n" to skip it) | string | n/a | — | — |
