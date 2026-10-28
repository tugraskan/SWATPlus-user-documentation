---
description: "Defines manure allocation objects that specify how manure from source objects is distributed to demand objects (HRUs, treatment plants, or interbasin diversions), including source locations, storage capacities, monthly production, and allocation rules with decision tables."
---

# manure_allo.mnu

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines manure allocation objects that specify how manure from source objects is distributed to demand objects (HRUs, treatment plants, or interbasin diversions), including source locations, storage capacities, monthly production, and allocation rules with decision tables.

SWAT+ uses the literal filename `manure_allo.mnu` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [manure_allocation_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/manure_allocation_read.f90#L39). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record.

### Record at line 42

Source condition/loop: `if (.not. i_exist .or. "manure_allo.mnu" == "null") then / else > do`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [imax](imax.md) | Total number of manure allocation objects defined in this file | integer | n/a | — | — |

### Record at line 51

Source condition/loop: `if (.not. i_exist .or. "manure_allo.mnu" == "null") then / else > do > do imro = 1, imax`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Name identifying the manure allocation object | string | n/a | — | — |
| [rule_typ](rule_typ.md) | Allocation rule type for the manure allocation object | string | n/a | — | — |
| [src_obs](src_obs.md) | Number of source objects providing manure to this allocation object | integer | n/a | — | — |
| [trn_obs](trn_obs.md) | Number of demand objects receiving manure from this allocation object | integer | n/a | — | — |

### Record at line 63

Source condition/loop: `if (.not. i_exist .or. "manure_allo.mnu" == "null") then / else > do > do imro = 1, imax > do isrc = 1, mallo(imro)%src_obs`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [i](i.md) | Leading integer identifier consumed by this source read | integer | n/a | — | — |

### Record at line 67

Source condition/loop: `if (.not. i_exist .or. "manure_allo.mnu" == "null") then / else > do > do imro = 1, imax > do isrc = 1, mallo(imro)%src_obs`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [k](k.md) | Leading integer identifier consumed by this source read | integer | n/a | — | — |
| [mois_typ](mois_typ.md) | Manure moisture-type selector | string | n/a | — | — |
| [manure_typ](manure_typ.md) | Manure type name referencing an entry in fertilizer.frt | string | n/a | — | — |
| [lat](lat.md) | Latitude of the source object | real | — | — | — |
| [long](long.md) | Longitude of the source object | real | — | — | — |
| [stor_init](stor_init.md) | Initial manure storage at the source object | real | — | — | — |
| [stor_max](stor_max.md) | Maximum manure storage capacity at the source object | real | — | — | — |
| [prod_mon](prod_mon.md) | Average monthly manure production at the source object | real | — | — | — |

### Record at line 90

Source condition/loop: `if (.not. i_exist .or. "manure_allo.mnu" == "null") then / else > do > do imro = 1, imax > do itrn = 1, num_objs`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [i](i.md) | Leading integer identifier consumed by this source read | integer | n/a | — | — |

### Record at line 94

Source condition/loop: `if (.not. i_exist .or. "manure_allo.mnu" == "null") then / else > do > do imro = 1, imax > do itrn = 1, num_objs`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [k](k.md) | Leading integer identifier consumed by this source read | integer | n/a | — | — |
| [ob_typ](ob_typ.md) | Type of demand object receiving manure: hru for application, muni for treatment plant, or divert for interbasin diversion | string | n/a | — | — |
| [ob_num](ob_num.md) | Number identifying the demand object of the specified type | integer | n/a | — | — |
| [dtbl](dtbl.md) | Name of the decision table governing manure or fertilizer application | string | n/a | — | — |
| [right](right.md) | Manure right designation, either sr for senior or jr for junior right | string | n/a | — | — |
