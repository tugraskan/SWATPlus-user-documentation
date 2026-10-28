---
description: "Defines landscape-level soft annual calibration targets for plant growth, organized by region and land use, used to compare simulated plant growth outputs against measured or desired values."
---

# plant_gro.sft

{% hint style="info" %}
The inspected Editor has a dispatched exporter for this input format; generation depends on project settings. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines landscape-level soft annual calibration targets for plant growth, organized by region and land use, used to compare simulated plant growth outputs against measured or desired values.

The reader obtains the filename through `in_chg%plant_gro_sft`.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record.

### Additional read at line 41

Source condition/loop: `if (.not. i_exist .or. in_chg%plant_gro_sft == "null" ) then / else > do`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [mreg](mreg.md) | Number of regions defined in this calibration input file | integer | n/a | — | — |

### Record at line 54

The repeated values follow count expression `nspu`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Name identifying a region containing a set of land uses for plant growth calibration | string | n/a | — | — |
| [lum_num](lum_num.md) | Number of land uses defined within this region | integer | n/a | — | — |
| [nspu](nspu.md) | Number of entries in the region element list | integer | n/a | — | — |
| [elem_cnt](elem_cnt.md) | Encoded element-list entry passed to define_unit_elements; repeated nspu times | integer | n/a | — | — |

### Record at line 86

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name_2.md) | Name of the measured or target plant growth value associated with this land use | string | n/a | — | — |
| [yield](yield.md) | Crop yield value used as a soft annual calibration target | real | — | — | — |
| [npp](npp.md) | Net primary productivity (biomass dry weight) value used as a soft annual calibration target | real | — | — | — |
| [lai_mx](lai_mx.md) | Maximum leaf area index value used as a soft annual calibration target | real | — | — | — |
| [wstress](wstress.md) | Sum of water (drought) stress value used as a soft annual calibration target | real | — | — | — |
| [astress](astress.md) | Sum of water (aeration) stress value used as a soft annual calibration target | real | — | — | — |
| [tstress](tstress.md) | Sum of temperature stress value used as a soft annual calibration target | real | — | — | — |
