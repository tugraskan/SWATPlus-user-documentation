---
description: User-defined parameter change records, object selections, and conditions for hard calibration.
---

# calibration.cal

Specifies hard-calibration parameter adjustments read into `cal_upd` (`update_parameters`, [`calibration_data_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L42)) by [`cal_parmchg_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parmchg_read.f90#L57-L158) and applied prior to simulation by [`cal_conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_conditions.f90#L48-L256) and [`cal_parm_select.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L69).

## Record count

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [mcal](mcal.md) | Number of parameter-change records in the file | integer | — | — | > 0 |

## Parameter-change records

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Parameter name matching `cal_parms.cal` | string | — | `""` | — |
| [chg\_type](chg_type.md) | Change mode (`absval`, `abschg`, `pctchg`, or `relchg`) | string | — | `""` | — |
| [val](val.md) | Magnitude of the parameter change | real | — | 0 | — |
| [conds](conds.md) | Number of conditional filter lines following this record | integer | — | 0 | >= 0 |
| [lyr1](lyr1.md) | First soil layer (or first `rdt` action index) | integer | — | 0 | >= 0 |
| [lyr2](lyr2.md) | Last soil layer (or second `rdt` action index) | integer | — | 0 | >= 0 |
| [year1](year1.md) | First year for climate changes (or third `rdt` action index) | integer | — | 0 | >= 0 |
| [year2](year2.md) | Last year for climate changes (or fourth `rdt` action index) | integer | — | 0 | >= 0 |
| [day1](day1.md) | First Julian day for climate changes (or fifth `rdt` action index) | integer | — | 0 | >= 0 |
| [day2](day2.md) | Last Julian day for climate changes | integer | — | 0 | >= 0 |
| [obj\_tot](obj_tot.md) | Count of object-selection tokens on the line (`0` selects defaults) | integer | — | 0 | >= 0 |
| [elements](elements.md) | Optional list of `obj_tot` integers selecting target objects/ranges | integer | — | — | — |

The file starts with a title line, the record count `mcal`, and a header line. When `obj_tot > 0`, the record continues with `obj_tot` integer entries (negative numbers denote inclusive ranges). When `obj_tot == 0`, [`cal_parmchg_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parmchg_read.f90#L106-L147) selects all default objects for the parameter's `obj_typ` in `cal_parms.cal`—for example, `gwf_riv` selects all SWAT-DEG channels (`sp_ob%chandeg`) and `gwf_sgl` selects the single global element (`1`).

For GWFlow `aquifer_delay`, [`cal_parm_select.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L1074-L1075) adjusts the delay in days rather than applying the change directly to $\alpha_{\text{gw}}$ and recomputes the recharge decay coefficient:

$$\alpha_{\text{gw}} = \exp\!\left(-\frac{1}{d_{\text{gw}} + 10^{-6}}\right)$$

where $\alpha_{\text{gw}}$ is the recharge decay coefficient (dimensionless) and $d_{\text{gw}}$ is the groundwater delay (`days`).

For `stream_bed`, [`cal_parm_select.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L1110-L1111) applies the change only when `ielem == 1` to avoid repeatedly modifying the same scalar variable (`gw_bed_change`).
