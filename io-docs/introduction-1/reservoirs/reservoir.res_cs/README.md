---
description: "Links reservoir records to named pesticide, weir, salt, and general-constituent entries."
---

# reservoir.res_cs

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Links reservoir records to named pesticide, weir, salt, and general-constituent entries.

SWAT+ uses the literal filename `reservoir.res_cs` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [res_read_salt_cs.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/res_read_salt_cs.f90#L31). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a header record, then a header record.

### Additional read at line 40

Source condition/loop: `if(i_exist) then > do i = 1, db_mx%res_dat`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [ires](ires.md) | integer counter identifying the reservoir record being read from the reservoir database | integer | n/a | — | — |

### Data record

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [k](k.md) | Leading integer identifier consumed by this source read | integer | n/a | — | — |
| [pst](pst.md) | character name of the pesticide input file (pesticide.res) linked to this reservoir | string | n/a | — | — |
| [weir](weir.md) | character name of the weir input file (weir.res) linked to this reservoir, added by Jaehak 2022 | string | n/a | — | — |
| [salt](salt.md) | character name of the salt input file (salt_res) linked to this reservoir | string | n/a | — | — |
| [cs](cs.md) | character name of the constituent input file (cs_res) linked to this reservoir | string | n/a | — | — |
