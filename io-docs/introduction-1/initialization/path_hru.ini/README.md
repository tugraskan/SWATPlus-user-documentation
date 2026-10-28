---
description: "Defines named sets of initial pathogen amounts in HRU soil and plant compartments."
---

# path_hru.ini

{% hint style="info" %}
The inspected Editor has a dispatched exporter for this input format; generation depends on project settings. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines named sets of initial pathogen amounts in HRU soil and plant compartments.

The reader obtains the filename through `in_init%path_soil`.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record, then a header record.

### Record at line 56

Source condition/loop: `if (i_exist .or. in_init%path_soil /= "null") then > do > do ipathi = 1, imax`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Name identifying this initial pathogen set | string | n/a | — | — |

### Record at line 58

Source condition/loop: `if (i_exist .or. in_init%path_soil /= "null") then > do > do ipathi = 1, imax`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [titldum](titldum.md) | Leading text label read before the compartment values | string | n/a | — | — |
| [soil](soil.md) | Initial soil-compartment value for each pathogen | real | — | — | — |
| [plt](plt.md) | Initial plant-compartment value for each pathogen | real | — | — | — |
