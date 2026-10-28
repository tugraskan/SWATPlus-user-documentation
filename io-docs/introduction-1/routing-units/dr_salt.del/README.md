---
description: "Defines salt delivery multiplier values applied to constituent hydrography at boundaries, read once per salt entry and matched to a named salts delivery file."
---

# dr_salt.del

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines salt delivery multiplier values applied to constituent hydrography at boundaries, read once per salt entry and matched to a named salts delivery file.

The reader obtains the filename through `in_delr%salt`.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record, then a header record, then a title record.

### Record at line 63

Source condition/loop: `if (i_exist .or. in_delr%salt /= "null") then > do > do ii = 1, db_mx%dr_salt`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [dr_salt_name(ii)](dr_salt_name_ii.md) | Name identifying this salt delivery record | string | n/a | — | — |
| [salt(isalt)](salt_isalt.md) | Delivery value for salt ion isalt | real | — | — | — |
