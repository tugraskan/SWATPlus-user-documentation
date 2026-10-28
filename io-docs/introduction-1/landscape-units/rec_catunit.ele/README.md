---
description: "Defines point-source cataloging-unit elements using object references and expansion fractions."
---

# rec_catunit.ele

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines point-source cataloging-unit elements using object references and expansion fractions.

The reader obtains the filename through `in_regs%ele_psc`.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record, then a header record.

### Additional read at line 159

Source condition/loop: `if (i_exist .or. in_regs%ele_psc /= "null") then > do > do isp = 1, imax`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [i](i.md) | Leading integer read during the file counting pass | integer | n/a | — | — |

### Data record

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [k](k.md) | Leading identifier read on the element data row | integer | n/a | — | — |
| [name](name.md) | Name of the categorical unit element | string | n/a | — | — |
| [obtyp](obtyp.md) | Object type label for this element | string | n/a | — | — |
| [obtypno](obtypno.md) | Identifier of the object of the specified type | integer | n/a | — | — |
| [bsn_frac](bsn_frac.md) | Fraction of the element in the basin (expansion factor) | real | — | — | — |
| [ru_frac](ru_frac.md) | Fraction of the element in the ru (expansion factor) | real | — | — | — |
| [reg_frac](reg_frac.md) | Fraction of the element in the calibration region (expansion factor) | real | — | — | — |
