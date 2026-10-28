---
description: "Defines atmospheric salt deposition inputs per weather station, organized by timestep (annual, monthly, or yearly), supplying salt-ion-specific rainfall and dry deposition values that are read when the salt database contains at least one salt entry."
---

# salt_atmo.cli

{% hint style="info" %}
The inspected Editor has a dispatched exporter for this input format; generation depends on project settings. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines atmospheric salt deposition inputs per weather station, organized by timestep (annual, monthly, or yearly), supplying salt-ion-specific rainfall and dry deposition values that are read when the salt database contains at least one salt entry.

SWAT+ uses the literal filename `salt_atmo.cli` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [cli_read_atmodep_salt.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/cli_read_atmodep_salt.f90#L33). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

### Record at line 52

Source condition/loop: `if(cs_db%num_salts > 0) then > if(i_exist) then > do iadep = 1, atmodep_cont%num_sta > if (atmodep_cont%timestep == "aa") then`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [station_name](station_name.md) | station_name is the identifier of the weather station associated with the annual atmospheric salt deposition record | string | n/a | — | — |

### Record at line 55

Source condition/loop: `if(cs_db%num_salts > 0) then > if(i_exist) then > do iadep = 1, atmodep_cont%num_sta > if (atmodep_cont%timestep == "aa") then > do isalt=1,cs_db%num_salts`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [salt_ion](salt_ion.md) | salt_ion is the four-character code naming the salt species for the annual rainfall concentration entry | string | n/a | — | — |
| [rf](rf.md) | rf is the annual average concentration of the salt ion in rainfall, expressed in mg/l, used to compute wet deposition of salt | real | — | — | — |

### Record at line 59

Source condition/loop: `if(cs_db%num_salts > 0) then > if(i_exist) then > do iadep = 1, atmodep_cont%num_sta > if (atmodep_cont%timestep == "aa") then > do isalt=1,cs_db%num_salts`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [salt_ion](salt_ion.md) | salt_ion is the four-character code naming the salt species for the annual dry deposition entry | string | n/a | — | — |
| [dry](dry.md) | dry is the annual dry deposition flux of the salt ion, expressed in kg/ha/yr, representing salt input from dry atmospheric fallout | real | — | — | — |

### Record at line 65

Source condition/loop: `if(cs_db%num_salts > 0) then > if(i_exist) then > do iadep = 1, atmodep_cont%num_sta > if (atmodep_cont%timestep == "mo") then`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [station_name](station_name.md) | station_name is the identifier of the weather station associated with the monthly atmospheric salt deposition records | string | n/a | — | — |

### Record at line 68

Source condition/loop: `if(cs_db%num_salts > 0) then > if(i_exist) then > do iadep = 1, atmodep_cont%num_sta > if (atmodep_cont%timestep == "mo") then > do isalt=1,cs_db%num_salts`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [salt_ion](salt_ion.md) | salt_ion is the four-character code naming the salt species for the monthly rainfall concentration entry | string | n/a | — | — |
| [rfmo(imo)](rfmo_imo.md) | rfmo(imo) is the monthly rainfall concentration of the salt ion for month imo, expressed in mg/l, providing timestep-specific wet deposition input | real | — | — | — |

### Record at line 72

Source condition/loop: `if(cs_db%num_salts > 0) then > if(i_exist) then > do iadep = 1, atmodep_cont%num_sta > if (atmodep_cont%timestep == "mo") then > do isalt=1,cs_db%num_salts`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [salt_ion](salt_ion.md) | salt_ion is the four-character code naming the salt species for the monthly dry deposition entry | string | n/a | — | — |
| [drymo(imo)](drymo_imo.md) | drymo(imo) is the monthly dry deposition flux of the salt ion for month imo, expressed in kg/ha/yr, providing timestep-specific dry deposition input | real | — | — | — |

### Record at line 78

Source condition/loop: `if(cs_db%num_salts > 0) then > if(i_exist) then > do iadep = 1, atmodep_cont%num_sta > if (atmodep_cont%timestep == "yr") then`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [station_name](station_name.md) | station_name is the identifier of the weather station associated with the yearly atmospheric salt deposition records | string | n/a | — | — |

### Record at line 81

Source condition/loop: `if(cs_db%num_salts > 0) then > if(i_exist) then > do iadep = 1, atmodep_cont%num_sta > if (atmodep_cont%timestep == "yr") then > do isalt=1,cs_db%num_salts`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [salt_ion](salt_ion.md) | salt_ion is the four-character code naming the salt species for the yearly rainfall concentration entry | string | n/a | — | — |
| [rfyr(iyr)](rfyr_iyr.md) | rfyr(iyr) is the yearly rainfall concentration of the salt ion for year iyr, expressed in mg/l, providing timestep-specific wet deposition input | real | — | — | — |

### Record at line 85

Source condition/loop: `if(cs_db%num_salts > 0) then > if(i_exist) then > do iadep = 1, atmodep_cont%num_sta > if (atmodep_cont%timestep == "yr") then > do isalt=1,cs_db%num_salts`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [salt_ion](salt_ion.md) | salt_ion is the four-character code naming the salt species for the yearly dry deposition entry | string | n/a | — | — |
| [dryyr(iyr)](dryyr_iyr.md) | dryyr(iyr) is the yearly dry deposition flux of the salt ion for year iyr, expressed in kg/ha/yr, providing timestep-specific dry deposition input | real | — | — | — |
