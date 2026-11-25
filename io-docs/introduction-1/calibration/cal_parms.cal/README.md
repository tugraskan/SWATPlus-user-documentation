---
description: Master lookup table defining calibratable parameter names, object types, and absolute bounds.
---

# cal\_parms.cal

{% hint style="info" %}
This file should not be modified by the user.
{% endhint %}

Defines valid calibration parameter names, associated object types, and absolute bounds, read into `cal_parms` ([`calibration_data_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L12)) by [`cal_parm_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_read.f90#L30-L42).

## Number of parameters

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [mchg\_par](mchg_par.md) | Number of calibration parameter records in the file | integer | — | — | > 0 |

## Parameter definitions

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Parameter identifier matched by `calibration.cal` | string | — | `default` | — |
| [obj\_typ](obj_typ.md) | Object type associated with the parameter | string | — | `plt` | — |
| [abs\_min](abs_min.md) | Minimum allowed parameter value after a calibration change | real | — | 0 | — |
| [abs\_max](abs_max.md) | Maximum allowed parameter value after a calibration change | real | — | 1e6 | — |
| [units](units.md) | Parameter units label (parsed but unused) | string | — | `null` | — |
