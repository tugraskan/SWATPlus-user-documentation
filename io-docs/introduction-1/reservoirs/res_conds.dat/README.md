---
description: "Defines reservoir release condition tables that govern when and how a reservoir releases water, each table holding a name plus counts of condition blocks and optional release modules, followed by repeated condition entries that compare a named source variable against a value with a two-character operator and apply a numeric action."
---

# res_conds.dat

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines reservoir release condition tables that govern when and how a reservoir releases water, each table holding a name plus counts of condition blocks and optional release modules, followed by repeated condition entries that compare a named source variable against a value with a two-character operator and apply a numeric action.

SWAT+ uses the literal filename `res_conds.dat` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [res_read_conds.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/res_read_conds.f90#L21). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record.

### Additional read at line 24

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [max_table](max_table.md) | Number of release condition tables to read for reservoirs | integer | n/a | — | — |

### Data record

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Name identifying this release condition table | string | n/a | — | — |
| [num_conds](num_conds.md) | Number of condition blocks defined for this table | integer | n/a | — | — |
| [num_modules](num_modules.md) | Number of release modules associated with this table | integer | n/a | — | — |

### Additional read at line 39

Source condition/loop: `do ictbl = 1, max_table > do ii = 1, ctbl(ictbl)%num_conds`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [isub_con](isub_con.md) | Number of source-variable comparisons in each condition block | integer | n/a | — | — |

### Additional read at line 42

Source condition/loop: `do ictbl = 1, max_table > do ii = 1, ctbl(ictbl)%num_conds`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [num_conds](num_conds_2.md) | Number of source-variable comparisons in this condition block | integer | n/a | — | — |
| [var](var.md) | Name of the source variable compared in this condition entry | string | n/a | — | — |
| [op](op.md) | Two-character comparison operator applied to the source variable | string | n/a | — | — |
| [val](val.md) | Value compared against the source variable | real | — | — | — |
| [action](action.md) | Numeric action applied when this condition block is satisfied | real | — | — | — |

### Additional read at line 48

Source condition/loop: `do ictbl = 1, max_table > do imod = 1, ctbl(ictbl)%num_modules`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [tnum_conds](tnum_conds.md) | Number of condition entries in each release module | integer | n/a | — | — |

### Additional read at line 54

Source condition/loop: `do ictbl = 1, max_table > do imod = 1, ctbl(ictbl)%num_modules > do ii = 1, tnum_conds`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [isub_con](isub_con.md) | Number of source-variable comparisons in each module condition entry | integer | n/a | — | — |

### Additional read at line 57

Source condition/loop: `do ictbl = 1, max_table > do imod = 1, ctbl(ictbl)%num_modules > do ii = 1, tnum_conds`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [num_conds](num_conds_3.md) | Number of source-variable comparisons in this module condition entry | integer | n/a | — | — |
| [var](var_2.md) | Name of the source variable compared in this module condition entry | string | n/a | — | — |
| [op](op_2.md) | Two-character comparison operator applied to the module source variable | string | n/a | — | — |
| [val](val_2.md) | Value compared against the module source variable | real | — | — | — |
| [action](action_2.md) | Numeric action applied when this module condition entry is satisfied | real | — | — | — |
