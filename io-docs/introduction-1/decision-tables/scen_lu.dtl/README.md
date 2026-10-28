---
description: "Defines scenario decision tables that link condition tests (object, variable, limit, operator, constant, alternatives) to action blocks (type, object, option, constants, file pointer, outcomes) used by the scenario decision logic."
---

# scen_lu.dtl

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines scenario decision tables that link condition tests (object, variable, limit, operator, constant, alternatives) to action blocks (type, object, option, constants, file pointer, outcomes) used by the scenario decision logic.

The reader obtains the filename through `in_cond%dtbl_scen`.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record.

### Record at line 38

Source condition/loop: `if (.not. i_exist .or. in_cond%dtbl_scen == "null") then / else > do`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [mdtbl](mdtbl.md) | count of decision tables defined in this file (used to size the table array) | integer | n/a | — | — |

### Record at line 47

Source condition/loop: `if (.not. i_exist .or. in_cond%dtbl_scen == "null") then / else > do > do i = 1, mdtbl`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | identifier of the decision table being defined | string | n/a | — | — |
| [conds](conds.md) | number of condition entries that follow for this table | integer | n/a | — | — |
| [alts](alts.md) | number of alternative condition sets evaluated for each condition | integer | n/a | — | — |
| [acts](acts.md) | number of action entries that follow for this table | integer | n/a | — | — |

### Record at line 64

Source condition/loop: `if (.not. i_exist .or. in_cond%dtbl_scen == "null") then / else > do > do i = 1, mdtbl > do ic = 1, dtbl_scen(i)%conds`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [var](var.md) | condition variable tested (e.g. volume, flow, sw, time) | string | n/a | — | — |
| [ob](ob.md) | object type the condition applies to (e.g. res, hru, canal) | string | n/a | — | — |
| [ob_num](ob_num.md) | numeric index of the object the condition applies to | integer | n/a | — | — |
| [lim_var](lim_var.md) | limit variable compared against (e.g. evol, pvol, fc, ul) | string | n/a | — | — |
| [lim_op](lim_op.md) | operator applied to the limit comparison (*, +, -) | string | n/a | — | — |
| [lim_const](lim_const.md) | constant value used in the limit comparison | real | — | — | — |
| [alt(ic,ial)](alt_ic_ial.md) | alternative value for condition ic under alternative set ial | string | n/a | — | — |

### Record at line 72

Source condition/loop: `if (.not. i_exist .or. in_cond%dtbl_scen == "null") then / else > do > do i = 1, mdtbl > do iac = 1, dtbl_scen(i)%acts`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [typ](typ.md) | type of action performed (e.g. reservoir release, irrigate, fertilize) | string | n/a | — | — |
| [ob](ob_2.md) | object type the action applies to (e.g. res, hru, canal) | string | n/a | — | — |
| [ob_num](ob_num_2.md) | numeric index of the object the action applies to | integer | n/a | — | — |
| [name](name_2.md) | identifier of the action | string | n/a | — | — |
| [option](option.md) | action option specific to its type (e.g. rate input, drawdown days, weir equation pointer) | string | n/a | — | — |
| [const](const.md) | primary constant for the action (e.g. rate, days) | real | — | — | — |
| [const2](const2.md) | secondary constant for the action (e.g. rate, days) | real | — | — | — |
| [file_pointer](file_pointer.md) | pointer referencing an external option (e.g. weir equation pointer) | string | n/a | — | — |
| [act_outcomes(iac,ial)](act_outcomes_iac_ial.md) | outcome flag for action iac under alternative ial ("y" performs the action, "n" does not) | string | n/a | — | — |
