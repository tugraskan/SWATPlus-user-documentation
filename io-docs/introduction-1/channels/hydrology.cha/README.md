---
description: "Defines per-reach channel hydraulic and geometric properties used by SWAT+ streamflow routing and channel process calculations, read through ch_read_hyd.f90."
---

# hydrology.cha

{% hint style="info" %}
The inspected Editor has a dispatched exporter for this input format; generation depends on project settings. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines per-reach channel hydraulic and geometric properties used by SWAT+ streamflow routing and channel process calculations, read through ch_read_hyd.f90.

The reader obtains the filename through `in_cha%hyd`.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record, then a header record, then a title record.

### Data record

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Identifier linking this channel hydraulic entry to a reach name defined in the channel data file | string | n/a | — | — |
| [w](w.md) | Average width of the main channel | real | — | — | — |
| [d](d.md) | Average depth of the main channel | real | — | — | — |
| [s](s.md) | Average longitudinal slope of the main channel | real | — | — | — |
| [l](l.md) | Length of the main channel within the subbasin | real | — | — | — |
| [n](n.md) | Manning's n roughness coefficient for the main channel | real | — | — | — |
| [k](k.md) | Leading integer identifier consumed by this source read | real | — | — | — |
| [wdr](wdr.md) | Ratio of channel width to depth | real | — | — | — |
| [alpha_bnk](alpha_bnk.md) | Alpha factor used in the bank storage recession curve | real | — | — | — |
| [side](side.md) | Change in horizontal distance per unit of vertical change on the channel side slope | real | — | — | — |
