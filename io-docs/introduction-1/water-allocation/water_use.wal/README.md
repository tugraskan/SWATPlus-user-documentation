---
description: "Defines water-use records with storage, lag, water-loss, and constituent source settings, plus additional pesticide and pathogen values when those databases are active."
---

# water_use.wal

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines water-use records with storage, lag, water-loss, and constituent source settings, plus additional pesticide and pathogen values when those databases are active.

SWAT+ uses the literal filename `water_use.wal` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [water_use_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/water_use_read.f90#L35). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record.

### Record at line 38

Source condition/loop: `if (.not. i_exist .or. 'water_use.wal' == "null") then / else > do`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [imax](imax.md) | the count of water-use object records to read from the file | integer | n/a | — | — |

### Record at line 48

Source condition/loop: `if (.not. i_exist .or. 'water_use.wal' == "null") then / else > do > do iwuse = 1, imax`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | the name of the water-use object | string | n/a | — | — |
| [stor_mx](stor_mx.md) | the maximum storage capacity of the object | real | — | — | — |
| [lag_days](lag_days.md) | the treatment lag time in days before outflow occurs | real | — | — | — |
| [loss_fr](loss_fr.md) | the fraction of water lost during treatment | real | — | — | — |
| [org_min_typ](org_min_typ.md) | the source type for organic/mineral constituent concentrations, one of const, dtbl, or recall | string | n/a | — | — |
| [org_min_name](org_min_name.md) | Name of the organic/mineral source record selected by the corresponding source-type field | string | n/a | — | — |
| [pests_typ](pests_typ.md) | the source type for pesticide concentrations, one of const, dtbl, or recall | string | n/a | — | — |
| [pests_name](pests_name.md) | Name of the pesticide source record selected by the corresponding source-type field | string | n/a | — | — |
| [paths_typ](paths_typ.md) | the source type for pathogen concentrations, one of const, dtbl, or recall | string | n/a | — | — |
| [paths_name](paths_name.md) | Name of the pathogen source record selected by the corresponding source-type field | string | n/a | — | — |
| [salts_typ](salts_typ.md) | the source type for salt ion concentrations, one of const, dtbl, or recall | string | n/a | — | — |
| [salts_name](salts_name.md) | Name of the salt source record selected by the corresponding source-type field | string | n/a | — | — |
| [constit_typ](constit_typ.md) | the source type for other constituent concentrations, one of const, dtbl, or recall | string | n/a | — | — |
| [constit_name](constit_name.md) | Name of the general-constituent source record selected by the corresponding source-type field | string | n/a | — | — |
| [descrip](descrip.md) | a description of the treatment object | string | n/a | — | — |

### Record at line 91

Source condition/loop: `if (.not. i_exist .or. 'water_use.wal' == "null") then / else > do > do iwuse = 1, imax > if (cs_db%num_pests > 0) then`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [pest](pest.md) | the pesticide loading value associated with this object, read only when pesticide constituents are defined | real | — | — | — |

### Record at line 98

Source condition/loop: `if (.not. i_exist .or. 'water_use.wal' == "null") then / else > do > do iwuse = 1, imax > if (cs_db%num_paths > 0) then`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [path](path.md) | the pathogen loading value associated with this object, read only when pathogen constituents are defined | real | — | — | — |
