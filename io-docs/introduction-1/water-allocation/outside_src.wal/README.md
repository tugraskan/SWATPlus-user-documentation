---
description: "Defines outside-source records and their constituent source types and names, with additional pesticide and pathogen values when those databases are active."
---

# outside_src.wal

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines outside-source records and their constituent source types and names, with additional pesticide and pathogen values when those databases are active.

SWAT+ uses the literal filename `outside_src.wal` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [water_osrc_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/water_osrc_read.f90#L34). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record.

### Record at line 37

Source condition/loop: `if (.not. i_exist .or. 'outside_src.wal' == "null") then / else > do`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [imax](imax.md) | count of outside-source (outside-source object) records to read from the file | integer | n/a | — | — |

### Record at line 47

Source condition/loop: `if (.not. i_exist .or. 'outside_src.wal' == "null") then / else > do > do isrc = 1, imax`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | identifier of the outside-source object for this outside-source record | string | n/a | — | — |
| [org_min_typ](org_min_typ.md) | resolution type for the organic/mineral constituent, one of const, dtbl, or recall | string | n/a | — | — |
| [org_min_name](org_min_name.md) | Name of the organic/mineral source record selected by the corresponding source-type field | string | n/a | — | — |
| [pests_typ](pests_typ.md) | resolution type for the pesticide constituent, one of const, dtbl, or recall | string | n/a | — | — |
| [pests_name](pests_name.md) | Name of the pesticide source record selected by the corresponding source-type field | string | n/a | — | — |
| [paths_typ](paths_typ.md) | resolution type for the pathogen constituent, one of const, dtbl, or recall | string | n/a | — | — |
| [paths_name](paths_name.md) | Name of the pathogen source record selected by the corresponding source-type field | string | n/a | — | — |
| [salts_typ](salts_typ.md) | resolution type for the salt ion constituent, one of const, dtbl, or recall | string | n/a | — | — |
| [salts_name](salts_name.md) | Name of the salt source record selected by the corresponding source-type field | string | n/a | — | — |
| [constit_typ](constit_typ.md) | resolution type for the other-constituent entry, one of const, dtbl, or recall | string | n/a | — | — |
| [constit_name](constit_name.md) | Name of the general-constituent source record selected by the corresponding source-type field | string | n/a | — | — |
| [descrip](descrip.md) | free-text description of the outside-source object | string | n/a | — | — |

### Record at line 90

Source condition/loop: `if (.not. i_exist .or. 'outside_src.wal' == "null") then / else > do > do isrc = 1, imax > if (cs_db%num_pests > 0) then`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [pest](pest.md) | pesticide concentration applied per object when the pesticides database is active | real | — | — | — |

### Record at line 97

Source condition/loop: `if (.not. i_exist .or. 'outside_src.wal' == "null") then / else > do > do isrc = 1, imax > if (cs_db%num_paths > 0) then`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [path](path.md) | pathogen concentration applied per object when the pathogens database is active | real | — | — | — |
