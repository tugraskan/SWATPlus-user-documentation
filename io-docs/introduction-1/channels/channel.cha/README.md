---
description: "Defines channel data records that link each channel to its initial, hydrology, sediment, and nutrient input files via named references resolved at runtime."
---

# channel.cha

{% hint style="info" %}
The inspected Editor has a dispatched exporter for this input format; generation depends on project settings. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines channel data records that link each channel to its initial, hydrology, sediment, and nutrient input files via named references resolved at runtime.

The reader obtains the filename through `in_cha%dat`.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record, then a header record.

### Additional read at line 61

Source condition/loop: `if (.not. i_exist .or. in_cha%dat == "null") then / else > do > do ichi = 1, db_mx%ch_dat`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [i](i.md) | Leading integer identifier consumed by this source read | integer | n/a | — | — |

### Data record

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [k](k.md) | Leading integer identifier consumed by this source read | integer | n/a | — | — |
| [name](name.md) | Character identifier naming the channel data record, used to match references from other files | string | n/a | — | — |
| [init](init.md) | Name of the initial channel record in initial.cha that this channel data references | string | n/a | — | — |
| [hyd](hyd.md) | Name of the hydrology record in hydrology.cha that provides hydrology inputs for this channel | string | n/a | — | — |
| [sed](sed.md) | Name of the sediment record in sediment.cha that provides sediment inputs for this channel | string | n/a | — | — |
| [nut](nut.md) | Name of the nutrient record in nutrients.cha that provides nutrient inputs for this channel | string | n/a | — | — |
