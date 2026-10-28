---
description: "Defines cataloging-unit elements using object types, object identifiers, and basin, routing-unit, and regional expansion fractions."
---

# element.ccu

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines cataloging-unit elements using object types, object identifiers, and basin, routing-unit, and regional expansion fractions.

SWAT+ uses the literal filename `element.ccu` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [ch_read_elements.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/ch_read_elements.f90#L145). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record, then a header record.

### Additional read at line 166

Source condition/loop: `if (i_exist ) then > do > do isp = 1, imax`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [i](i.md) | Leading integer read during the file counting pass | integer | n/a | — | — |

### Data record

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [k](k.md) | Leading identifier read on the element data row | integer | n/a | — | — |
| [name](name.md) | Character name (up to 16 characters) identifying the custom calibration element | string | n/a | — | — |
| [obtyp](obtyp.md) | Object type label for this element | string | n/a | — | — |
| [obtypno](obtypno.md) | Identifier of the object of the specified type | integer | n/a | — | — |
| [bsn_frac](bsn_frac.md) | Real fraction of the element area within the basin, used as an expansion factor for basin-level distribution | real | — | — | — |
| [ru_frac](ru_frac.md) | Real fraction of the element area within a reach/zone unit, used as an expansion factor for reach-level distribution | real | — | — | — |
| [reg_frac](reg_frac.md) | Real fraction of the element area within a calibration region, used as an expansion factor for region-level distribution | real | — | — | — |
