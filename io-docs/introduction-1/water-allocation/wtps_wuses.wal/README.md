---
description: "The wtps_wuses.wal file declares the number of water treatment plant objects and water use objects to be simulated, followed by their respective names. The first record provides the counts used to allocate downstream arrays, and subsequent records list one name per object for matching against database entries."
---

# wtps_wuses.wal

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

The wtps_wuses.wal file declares the number of water treatment plant objects and water use objects to be simulated, followed by their respective names. The first record provides the counts used to allocate downstream arrays, and subsequent records list one name per object for matching against database entries.

SWAT+ uses the literal filename `wtps_wuses.wal` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [wallo_wtps_wuses.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/wallo_wtps_wuses.f90#L27). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record.

### Record at line 32

Source condition/loop: `if (i_exist .or. 'wtps_wuses.wal' /= "null") then > do`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [wtps](wtps.md) | Number of water treatment plant objects included in the simulation, used to size related arrays | integer | n/a | — | — |
| [wuses](wuses.md) | Number of water use objects included in the simulation, used to size related arrays and drive loops over water use entries | integer | n/a | — | — |

### Record at line 56

Source condition/loop: `if (i_exist .or. 'wtps_wuses.wal' /= "null") then > do`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [wtp_name(iwtp)](wtp_name_iwtp.md) | Name of a single water treatment plant object, matched against database records to associate the object with its definition | string | n/a | — | — |

### Record at line 59

Source condition/loop: `if (i_exist .or. 'wtps_wuses.wal' /= "null") then > do`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [wuse_name(iwuse)](wuse_name_iwuse.md) | Name of a single water use object, matched against database records to associate the object with its definition | string | n/a | — | — |
