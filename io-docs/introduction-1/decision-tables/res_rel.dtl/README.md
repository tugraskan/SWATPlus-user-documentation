---
description: "Defines reservoir release decision tables that evaluate conditions (such as storage, inflow, or time) against alternatives to determine release actions for a given reservoir. Each table lists condition variables, their comparison limits, the action to take, and the outcome flags for each alternative."
---

# res_rel.dtl

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines reservoir release decision tables that evaluate conditions (such as storage, inflow, or time) against alternatives to determine release actions for a given reservoir. Each table lists condition variables, their comparison limits, the action to take, and the outcome flags for each alternative.

The reader obtains the filename through `in_cond%dtbl_res`.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record.

### Record at line 39

Source condition/loop: `if (.not. i_exist .or. in_cond%dtbl_res == "null") then / else > do`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [mdtbl](mdtbl.md) | number of reservoir release decision tables defined in the file | integer | n/a | — | — |

### Record at line 48

Source condition/loop: `if (.not. i_exist .or. in_cond%dtbl_res == "null") then / else > do > do i = 1, mdtbl`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | identifier of the decision table, matched against the release name in reservoir data | string | n/a | — | — |
| [conds](conds.md) | count of condition entries that follow for this decision table | integer | n/a | — | — |
| [alts](alts.md) | count of alternatives evaluated for each condition in this decision table | integer | n/a | — | — |
| [acts](acts.md) | count of actions defined for this decision table | integer | n/a | — | — |

### Record at line 62

Source condition/loop: `if (.not. i_exist .or. in_cond%dtbl_res == "null") then / else > do > do i = 1, mdtbl > do ic = 1, dtbl_res(i)%conds`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [var](var.md) | condition variable being evaluated (e.g. volume, flow, sw, time) | string | n/a | — | — |
| [ob](ob.md) | object type the condition variable applies to (e.g. res, hru, canal) | string | n/a | — | — |
| [ob_num](ob_num.md) | index of the object the condition variable applies to | integer | n/a | — | — |
| [lim_var](lim_var.md) | limit variable compared against the condition variable (e.g. evol, pvol, fc, ul) | string | n/a | — | — |
| [lim_op](lim_op.md) | operator applied when comparing the condition variable to the limit variable (*, +, -) | string | n/a | — | — |
| [lim_const](lim_const.md) | constant value used in the limit comparison for the condition | real | — | — | — |
| [alt(ic,ial)](alt_ic_ial.md) | alternative value for condition ic and alternative ial | string | n/a | — | — |

### Record at line 70

Source condition/loop: `if (.not. i_exist .or. in_cond%dtbl_res == "null") then / else > do > do i = 1, mdtbl > do iac = 1, dtbl_res(i)%acts`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [typ](typ.md) | type of action to perform (e.g. reservoir release, irrigate, fertilize) | string | n/a | — | — |
| [ob](ob_2.md) | object type the action applies to (e.g. res, hru, canal) | string | n/a | — | — |
| [ob_num](ob_num_2.md) | index of the object the action applies to | integer | n/a | — | — |
| [name](name_2.md) | name of the action | string | n/a | — | — |
| [option](option.md) | action-specific option (e.g. rate input, drawdown days, weir equation pointer) | string | n/a | — | — |
| [const](const.md) | constant used for the action (e.g. rate, days) | real | — | — | — |
| [const2](const2.md) | additional constant used for the action (e.g. secondary rate, days) | real | — | — | — |
| [file_pointer](file_pointer.md) | name of the referenced option file (e.g. weir equation or recall data) | string | n/a | — | — |
| [act_outcomes(iac,ial)](act_outcomes_iac_ial.md) | outcome flag for action iac and alternative ial ("y" to perform, "n" to skip) | string | n/a | — | — |
