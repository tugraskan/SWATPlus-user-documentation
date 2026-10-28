---
description: "Defines named sets of initial heavy-metal amounts in HRU soil and plant compartments."
---

# hmet_hru.ini

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines named sets of initial heavy-metal amounts in HRU soil and plant compartments.

The reader obtains the filename through `in_init%hmet_soil`.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record, then a header record.

### Record at line 57

Source condition/loop: `if (i_exist .or. in_init%hmet_soil /= "null") then > do > do ihmeti = 1, imax`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Name identifying this set of initial constituent values | string | n/a | — | — |

### Record at line 60

Source condition/loop: `if (i_exist .or. in_init%hmet_soil /= "null") then > do > do ihmeti = 1, imax > do ipest = 1, cs_db%num_metals`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [titldum](titldum.md) | Leading text label read before the compartment values | string | n/a | — | — |
| [soil(ihmet)](soil_ihmet.md) | amount of constituent in soil at start of simulation | real | — | — | — |

### Record at line 62

Source condition/loop: `if (i_exist .or. in_init%hmet_soil /= "null") then > do > do ihmeti = 1, imax > do ipest = 1, cs_db%num_metals`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [titldum](titldum.md) | Leading text label read before the compartment values | string | n/a | — | — |
| [plt(ihmet)](plt_ihmet.md) | amount of constituent on plant at start of simulation | real | — | — | — |
