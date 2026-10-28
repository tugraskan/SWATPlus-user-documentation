---
description: "Defines region elements for HRUs, LSU, or hru_lte objects, read when in_regs%ele_reg is set, with each data record specifying an object type, identifier, and area in hectares."
---

# ls_reg.ele

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines region elements for HRUs, LSU, or hru_lte objects, read when in_regs%ele_reg is set, with each data record specifying an object type, identifier, and area in hectares.

The reader obtains the filename through `in_regs%ele_reg`.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record, then a header record.

### Additional read at line 155

Source condition/loop: `if (i_exist .or. in_regs%ele_reg /= "null") then > do > do isp = 1, imax`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [i](i.md) | Leading integer read during the file counting pass | integer | n/a | — | — |

### Data record

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [k](k.md) | Leading identifier read on the element data row | integer | n/a | — | — |
| [name](name.md) | Name identifier for the region element | string | n/a | — | — |
| [ha](ha.md) | Area of the region element in hectares | real | — | — | — |
| [obtyp](obtyp.md) | Object type label for this element | string | n/a | — | — |
| [obtypno](obtypno.md) | Identifier of the object of the specified type | integer | n/a | — | — |
