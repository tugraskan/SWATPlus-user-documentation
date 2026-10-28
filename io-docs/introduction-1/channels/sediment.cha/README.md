---
description: "Defines per-channel sediment characteristics for channel erosion and deposition routing, including the selected sediment transport method and monthly erodibility values used by the channel sediment routine."
---

# sediment.cha

{% hint style="info" %}
The inspected Editor has a dispatched exporter for this input format; generation depends on project settings. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines per-channel sediment characteristics for channel erosion and deposition routing, including the selected sediment transport method and monthly erodibility values used by the channel sediment routine.

The reader obtains the filename through `in_cha%sed`.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record, then a header record, then a title record.

### Data record

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Name identifying the channel reach whose sediment properties are described | string | n/a | — | — |
| [eqn](eqn.md) | Selects the sediment transport equation applied to this channel: 0 = original SWAT, 1 = Bagnold, 2 = Kodatie, 3 = Molinas-WU, 4 = Yang | integer | n/a | — | — |
| [cov1](cov1.md) | Channel bank erodibility factor scaling the computed bank critical shear stress | real | — | — | — |
| [cov2](cov2.md) | Channel bed cover factor scaling the computed bed critical shear stress | real | — | — | — |
| [bnk_bd](bnk_bd.md) | Bulk density of the channel bank sediment | real | — | — | — |
| [bed_bd](bed_bd.md) | Bulk density of the channel bed sediment | real | — | — | — |
| [bnk_kd](bnk_kd.md) | Jet-test-derived erodibility of the channel bank sediment | real | — | — | — |
| [bed_kd](bed_kd.md) | Jet-test-derived erodibility of the channel bed sediment | real | — | — | — |
| [bnk_d50](bnk_d50.md) | Median (D50) particle size diameter of the channel bank sediment | real | — | — | — |
| [bed_d50](bed_d50.md) | Median (D50) particle size diameter of the channel bed sediment | real | — | — | — |
| [tc_bnk](tc_bnk.md) | Critical shear stress required to initiate motion of the channel bank | real | — | — | — |
| [tc_bed](tc_bed.md) | Critical shear stress required to initiate motion of the channel bed | real | — | — | — |
| [erod(1)](erod_1.md) | Monthly (January) channel erodibility, where 0.0 is non-erosive and 1.0 indicates no resistance to erosion | real | — | — | — |
| [erod(2)](erod_2.md) | Monthly (February) channel erodibility, where 0.0 is non-erosive and 1.0 indicates no resistance to erosion | real | — | — | — |
| [erod(3)](erod_3.md) | Monthly (March) channel erodibility, where 0.0 is non-erosive and 1.0 indicates no resistance to erosion | real | — | — | — |
| [erod(4)](erod_4.md) | Monthly (April) channel erodibility, where 0.0 is non-erosive and 1.0 indicates no resistance to erosion | real | — | — | — |
| [erod(5)](erod_5.md) | Monthly (May) channel erodibility, where 0.0 is non-erosive and 1.0 indicates no resistance to erosion | real | — | — | — |
| [erod(6)](erod_6.md) | Monthly (June) channel erodibility, where 0.0 is non-erosive and 1.0 indicates no resistance to erosion | real | — | — | — |
| [erod(7)](erod_7.md) | Monthly (July) channel erodibility, where 0.0 is non-erosive and 1.0 indicates no resistance to erosion | real | — | — | — |
| [erod(8)](erod_8.md) | Monthly (August) channel erodibility, where 0.0 is non-erosive and 1.0 indicates no resistance to erosion | real | — | — | — |
| [erod(9)](erod_9.md) | Monthly (September) channel erodibility, where 0.0 is non-erosive and 1.0 indicates no resistance to erosion | real | — | — | — |
| [erod(10)](erod_10.md) | Monthly (October) channel erodibility, where 0.0 is non-erosive and 1.0 indicates no resistance to erosion | real | — | — | — |
| [erod(11)](erod_11.md) | Monthly (November) channel erodibility, where 0.0 is non-erosive and 1.0 indicates no resistance to erosion | real | — | — | — |
| [erod(12)](erod_12.md) | Monthly (December) channel erodibility, where 0.0 is non-erosive and 1.0 indicates no resistance to erosion | real | — | — | — |
