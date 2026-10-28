---
description: "Links wetland records to named pesticide, weir, salt, and general-constituent entries."
---

# wetland.wet_cs

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Links wetland records to named pesticide, weir, salt, and general-constituent entries.

SWAT+ uses the literal filename `wetland.wet_cs` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [wet_read_salt_cs.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/wet_read_salt_cs.f90#L31). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a header record, then a header record.

### Additional read at line 40

Source condition/loop: `if(i_exist) then > do iwet = 1, db_mx%wet_dat`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [i](i.md) | Leading integer identifier consumed by this source read | integer | n/a | — | — |

### Data record

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [k](k.md) | Leading integer identifier consumed by this source read | integer | n/a | — | — |
| [pst](pst.md) | Name of the pesticide input source linked to this wetland, referencing an entry in pesticide.res | string | n/a | — | — |
| [weir](weir.md) | Name of the weir input source linked to this wetland, referencing an entry in weir.res | string | n/a | — | — |
| [salt](salt.md) | Name of the salt input source linked to this wetland, referencing an entry in the salt_res table | string | n/a | — | — |
| [cs](cs.md) | Name of the constituent input source linked to this wetland, referencing an entry in the cs_res table | string | n/a | — | — |
