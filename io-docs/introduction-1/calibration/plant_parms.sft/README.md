---
description: Regional plant parameter initial values and bounds for soft calibration.
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

Specifies plant soft-calibration parameter initial values and iteration bounds by region, read into `pl_prms` ([`calibration_data_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L172)) by [`pl_read_parms_cal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_read_parms_cal.f90#L37-L118).

# plant\_parms.sft

After the title, region count, and headings, enter the region header and HRU element list, followed by `lum_num * parms` plant-parameter rows.

{% hint style="warning" %}
In SWAT+ main (`6f515368`), [`pl_read_parms_cal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_read_parms_cal.f90#L48-L53) reads `name, lum_num, parms, nspu` at line 48, then when `nspu > 0` backspaces and re-reads `name, lum_num, nspu, elem_cnt` at line 53 (omitting `parms`), so `parms` retains its struct default (`2`) while reading column 3 as `nspu`. Also, [`calsoft_plant.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_plant.f90#L93-L516) and [`pl_write_parms_cal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_write_parms_cal.f90#L32-L54) index parameter rows in fixed `lum_num`-sized blocks ordered `pest_stress`, `epco`, `lai_pot`, and `harv_idx`.
{% endhint %}

## Region count

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [mreg](mreg.md) | Number of plant soft-calibration regions | integer | — | — | > 0 |

## Regions and elements

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Region name | string | — | `default` | — |
| [lum\_num](lum_num.md) | Number of land uses or plants defined in the region | integer | — | 0 | > 0 |
| [parms](parms.md) | Number of plant parameters calibrated per land use | integer | — | 2 | > 0 |
| [nspu](nspu.md) | Number of HRU element-list tokens on the region row | integer | — | 0 | >= 0 |
| [elem\_cnt](elem_cnt.md) | HRU indices or ranges (`-`) included in the region | integer | — | — | — |

## Plant parameters

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [var](var.md) | Plant parameter variable name (`epco`, `pest_stress`, `lai_pot`, or `harv_idx`) | string | — | `default` | — |
| [name](name_2.md) | Plant or crop name matched against simulated plants | string | — | `default` | — |
| [init\_val](init_val.md) | Initial value assigned to the plant parameter | real | — | 0 | — |
| [chg\_typ](chg_typ.md) | Change type label (parsed but unused) | string | — | `""` | — |
| [neg](neg.md) | Lower iteration limit on the calibrated parameter | real | — | 0 | — |
| [pos](pos.md) | Upper iteration limit on the calibrated parameter | real | — | 0 | — |
| [lo](lo.md) | Absolute lower bound clamped on the plant parameter | real | — | 0 | — |
| [up](up.md) | Absolute upper bound clamped on the plant parameter | real | — | 0 | — |
