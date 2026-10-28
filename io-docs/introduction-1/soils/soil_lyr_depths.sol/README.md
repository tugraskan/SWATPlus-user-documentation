---
description: "Supplies custom cumulative soil-layer depths used while constructing the model soil layers. The reader counts and rereads the depth records and inserts a 10 mm surface layer."
---

# soil_lyr_depths.sol

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Supplies custom cumulative soil-layer depths used while constructing the model soil layers. The reader counts and rereads the depth records and inserts a 10 mm surface layer.

SWAT+ uses the literal filename `soil_lyr_depths.sol` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [soils_init.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/soils_init.f90#L166). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record, then a header record.

### Record at line 206

Source condition/loop: `do isol = 1, msoils > if (.not. i_exist) then / else`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [units](units.md) | Units text token read before the depth values | string | n/a | — | — |

### Record at line 212

Source condition/loop: `do isol = 1, msoils > if (.not. i_exist) then / else > do i = 1, mlyr > do`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [csld](csld.md) | Cumulative custom soil-layer depth used to construct layer boundaries | integer | n/a | — | — |
