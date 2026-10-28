---
description: "Defines calibration parameters for plant growth across land-use regions, including per-region counts of land uses and parameters, per-parameter initial values and change types, and per-iteration negative/positive and absolute lower/upper limits applied during calibration."
---

# plant_parms.sft

{% hint style="info" %}
The inspected Editor has a dispatched exporter for this input format; generation depends on project settings. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines calibration parameters for plant growth across land-use regions, including per-region counts of land uses and parameters, per-parameter initial values and change types, and per-iteration negative/positive and absolute lower/upper limits applied during calibration.

The reader obtains the filename through `in_chg%plant_parms_sft`.

{% hint style="warning" %}
The first region read includes `parms` before `nspu`, but the backspaced reread omits `parms` (pl_read_parms_cal.f90:48–53). Both source variants are shown below. They are not two successive input records; the discrepancy prevents these tables from being treated as a validated file template.
{% endhint %}

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record.

### Additional read at line 40

Source condition/loop: `if (.not. i_exist .or. in_chg%plant_parms_sft == "null") then / else > do`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [mreg](mreg.md) | Number of calibration regions to allocate and read | integer | n/a | — | — |

### Record at line 48

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Name identifying this group, region, or parameter set | string | n/a | — | — |
| [lum_num](lum_num.md) | Number of land uses defined within the region | integer | n/a | — | — |
| [parms](parms.md) | Number of plant parameters used in calibration for the region | integer | n/a | — | — |
| [nspu](nspu.md) | Number of entries in the region element list | integer | n/a | — | — |

### Record at line 53

The repeated values follow count expression `nspu`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Name identifying this group, region, or parameter set | string | n/a | — | — |
| [lum_num](lum_num.md) | Number of land uses defined within the region | integer | n/a | — | — |
| [nspu](nspu.md) | Number of entries in the region element list | integer | n/a | — | — |
| [elem_cnt](elem_cnt.md) | Encoded element-list entry passed to define_unit_elements | integer | n/a | — | — |

### Record at line 83

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [var](var.md) | Variable name identifying which plant parameter is being calibrated | string | n/a | — | — |
| [name](name_2.md) | Name identifying this group, region, or parameter set | string | n/a | — | — |
| [init_val](init_val.md) | Initial calibration value for the named plant parameter | real | — | — | — |
| [chg_typ](chg_typ.md) | Type of change applied to the parameter during calibration (absval, abschg, or pctchg) | string | n/a | — | — |
| [neg](neg.md) | Negative limit applied to the parameter per calibration iteration | real | — | — | — |
| [pos](pos.md) | Positive limit applied to the parameter per calibration iteration | real | — | — | — |
| [lo](lo.md) | Ultimate lower limit of the parameter, enforced via a Max operation | real | — | — | — |
| [up](up.md) | Ultimate upper limit of the parameter, enforced via an amin1 operation | real | — | — | — |
