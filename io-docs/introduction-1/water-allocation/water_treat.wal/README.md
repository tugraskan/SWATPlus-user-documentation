---
description: "Defines water treatment plants and their removal of organic/mineral, pesticide, pathogen, salt, and other constituent loads from routed streamflow, with per-plant storage, lag, loss, and per-treatment-level concentration targets."
---

# water_treat.wal

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines water treatment plants and their removal of organic/mineral, pesticide, pathogen, salt, and other constituent loads from routed streamflow, with per-plant storage, lag, loss, and per-treatment-level concentration targets.

SWAT+ uses the literal filename `water_treat.wal` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [water_treatment_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/water_treatment_read.f90#L34). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record.

### Record at line 37

Source condition/loop: `if (.not. i_exist .or. 'water_treat.wal' == "null") then / else > do`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [imax](imax.md) | number of water treatment plants defined in this file | integer | n/a | — | — |

### Record at line 45

Source condition/loop: `if (.not. i_exist .or. 'water_treat.wal' == "null") then / else > do > do iwtp = 1, imax`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | identifier of the water treatment plant | string | n/a | — | — |
| [stor_mx](stor_mx.md) | maximum storage capacity of the treatment plant | real | — | — | — |
| [lag_days](lag_days.md) | lag time applied to treated outflow from the plant | real | — | — | — |
| [loss_fr](loss_fr.md) | fraction of water lost during treatment | real | — | — | — |
| [num_treats](num_treats.md) | number of treatment levels defined for this plant | integer | n/a | — | — |

### Record at line 51

Source condition/loop: `if (.not. i_exist .or. 'water_treat.wal' == "null") then / else > do > do iwtp = 1, imax > do itrt = 1, wtp(iwtp)%num_treats`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [org_min_typ](org_min_typ.md) | source type for organic/mineral removal, one of const, dtbl, or recall | string | n/a | — | — |
| [org_min_name](org_min_name.md) | Name of the organic/mineral source record selected by the corresponding source-type field | string | n/a | — | — |
| [pests_typ](pests_typ.md) | source type for pesticide removal, one of const, dtbl, or recall | string | n/a | — | — |
| [pests_name](pests_name.md) | Name of the pesticide source record selected by the corresponding source-type field | string | n/a | — | — |
| [paths_typ](paths_typ.md) | source type for pathogen removal, one of const, dtbl, or recall | string | n/a | — | — |
| [paths_name](paths_name.md) | Name of the pathogen source record selected by the corresponding source-type field | string | n/a | — | — |
| [salts_typ](salts_typ.md) | source type for salt ion removal, one of const, dtbl, or recall | string | n/a | — | — |
| [salts_name](salts_name.md) | Name of the salt source record selected by the corresponding source-type field | string | n/a | — | — |
| [constit_typ](constit_typ.md) | source type for other constituent removal, one of const, dtbl, or recall | string | n/a | — | — |
| [constit_name](constit_name.md) | Name of the general-constituent source record selected by the corresponding source-type field | string | n/a | — | — |
| [descrip](descrip.md) | descriptive text for the treatment plant | string | n/a | — | — |

### Record at line 105

Source condition/loop: `if (.not. i_exist .or. 'water_treat.wal' == "null") then / else > do > do iwtp = 1, imax > do itrt = 1, wtp(iwtp)%num_treats > if (cs_db%num_pests > 0) then`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [pest](pest.md) | pesticide removal amount applied per pesticide, read when pesticides are present | real | — | — | — |

### Record at line 112

Source condition/loop: `if (.not. i_exist .or. 'water_treat.wal' == "null") then / else > do > do iwtp = 1, imax > do itrt = 1, wtp(iwtp)%num_treats > if (cs_db%num_paths > 0) then`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [path](path.md) | pathogen removal amount applied per pathogen, read when pathogens are present | real | — | — | — |
