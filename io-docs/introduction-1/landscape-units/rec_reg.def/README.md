---
description: "Defines point-source calibration regions, their areas, and element lists, preceded by a region count."
---

# rec_reg.def

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines point-source calibration regions, their areas, and element lists, preceded by a region count.

The reader obtains the filename through `in_regs%def_psc_reg`.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record.

### Additional read at line 86

Source condition/loop: `if (i_exist .or. in_regs%def_psc_reg /= "null") then > do`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [mreg](mreg.md) | Number of group or region records to read | integer | n/a | — | — |

### Data record

The repeated values follow count expression `nspu`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [k](k.md) | Leading record identifier read before the group or region fields | integer | n/a | — | — |
| [name](name.md) | Name identifying the region | string | n/a | — | — |
| [area_ha](area_ha.md) | Area of the region in hectares | real | — | — | — |
| [nspu](nspu.md) | Number of encoded element-list entries for this group or region | integer | n/a | — | — |
| [elem_cnt](elem_cnt.md) | Encoded element-list entry passed to define_unit_elements | integer | n/a | — | — |
