---
description: "Defines atmospheric contaminant inputs for a single station, with separate records selected by the station's timestep (\"aa\" annual, \"mo\" monthly, or \"yr\" yearly) supplying rainfall and dry-deposition concentrations applied per constituent."
---

# cs_atmo.cli

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines atmospheric contaminant inputs for a single station, with separate records selected by the station's timestep ("aa" annual, "mo" monthly, or "yr" yearly) supplying rainfall and dry-deposition concentrations applied per constituent.

SWAT+ uses the literal filename `cs_atmo.cli` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [cli_read_atmodep_cs.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/cli_read_atmodep_cs.f90#L32). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

### Record at line 48

Source condition/loop: `if(cs_db%num_cs > 0) then > if(i_exist) then > do iadep = 1, atmodep_cont%num_sta > if (atmodep_cont%timestep == "aa") then`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [station_name](station_name.md) | Station identifier for the annual timestep record (station_name) | real | — | — | — |

### Record at line 51

Source condition/loop: `if(cs_db%num_cs > 0) then > if(i_exist) then > do iadep = 1, atmodep_cont%num_sta > if (atmodep_cont%timestep == "aa") then > do ics=1,cs_db%num_cs`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [rf](rf.md) | Annual rainfall concentration of the constituent in rainfall (mg/L), scaled by precipitation to compute mass loading | real | — | — | — |

### Record at line 55

Source condition/loop: `if(cs_db%num_cs > 0) then > if(i_exist) then > do iadep = 1, atmodep_cont%num_sta > if (atmodep_cont%timestep == "aa") then > do ics=1,cs_db%num_cs`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [dry](dry.md) | Annual dry deposition flux of the constituent (kg/ha/yr), divided by 365 to obtain a daily rate | real | — | — | — |

### Record at line 61

Source condition/loop: `if(cs_db%num_cs > 0) then > if(i_exist) then > do iadep = 1, atmodep_cont%num_sta > if (atmodep_cont%timestep == "mo") then`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [station_name](station_name.md) | Station identifier for the monthly timestep record (station_name) | real | — | — | — |

### Record at line 67

Source condition/loop: `if(cs_db%num_cs > 0) then > if(i_exist) then > do iadep = 1, atmodep_cont%num_sta > if (atmodep_cont%timestep == "mo") then > do ics=1,cs_db%num_cs`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [rfmo(imo)](rfmo_imo.md) | Monthly rainfall concentration of the constituent for month imo, scaled by monthly precipitation to compute mass loading | real | — | — | — |

### Record at line 74

Source condition/loop: `if(cs_db%num_cs > 0) then > if(i_exist) then > do iadep = 1, atmodep_cont%num_sta > if (atmodep_cont%timestep == "mo") then > do ics=1,cs_db%num_cs`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [drymo(imo)](drymo_imo.md) | Monthly dry deposition flux of the constituent for month imo, divided by a time-conversion constant to obtain a daily rate | real | — | — | — |

### Record at line 80

Source condition/loop: `if(cs_db%num_cs > 0) then > if(i_exist) then > do iadep = 1, atmodep_cont%num_sta > if (atmodep_cont%timestep == "yr") then`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [station_name](station_name.md) | Station identifier for the yearly timestep record (station_name) | real | — | — | — |

### Record at line 86

Source condition/loop: `if(cs_db%num_cs > 0) then > if(i_exist) then > do iadep = 1, atmodep_cont%num_sta > if (atmodep_cont%timestep == "yr") then > do ics=1,cs_db%num_cs`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [rfyr(iyr)](rfyr_iyr.md) | Yearly rainfall concentration of the constituent for year iyr, scaled by yearly precipitation to compute mass loading | real | — | — | — |

### Record at line 93

Source condition/loop: `if(cs_db%num_cs > 0) then > if(i_exist) then > do iadep = 1, atmodep_cont%num_sta > if (atmodep_cont%timestep == "yr") then > do ics=1,cs_db%num_cs`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [dryyr(iyr)](dryyr_iyr.md) | Yearly dry deposition flux of the constituent for year iyr, divided by 365 to obtain a daily rate | real | — | — | — |
