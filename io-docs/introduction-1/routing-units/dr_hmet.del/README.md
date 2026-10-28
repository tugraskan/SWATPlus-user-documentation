---
description: "Provides heavy metals delivery definitions for the hydrologic delivery routing (dr) component, read when a hydrography delivery hmet entry exists or is referenced as non-null."
---

# dr_hmet.del

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Provides heavy metals delivery definitions for the hydrologic delivery routing (dr) component, read when a hydrography delivery hmet entry exists or is referenced as non-null.

The reader obtains the filename through `in_delr%hmet`.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record, then a header record, then a title record.

### Record at line 64

Source condition/loop: `if (i_exist .or. in_delr%hmet /= "null") then > do > do ii = 1, db_mx%dr_hmet`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [dr_hmet_name(ii)](dr_hmet_name_ii.md) | Name identifying a heavy metals delivery definition (dr_hmet_name), matched against the hmet_file value to select the delivery record | string | n/a | — | — |
| [hmet(ihmet)](hmet_ihmet.md) | Heavy metals delivery value (hmet) associated with the named delivery definition | real | — | — | — |
