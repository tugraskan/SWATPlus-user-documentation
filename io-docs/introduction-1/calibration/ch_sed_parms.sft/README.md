---
description: Channel sediment parameters and change limits for soft calibration.
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

Specifies channel sediment parameters and bounds for soft calibration, read into `ch_prms` ([`calibration_data_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L80)) by [`ch_read_parms_cal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_parms_cal.f90#L22-L40).

# ch\_sed\_parms.sft

## Number of parameters

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [mchp](mchp.md) | Number of channel sediment calibration parameter rows | integer | — | — | > 0 |

## Parameter bounds

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Parameter name (first entry echoed to `hru-new.cal`) | string | — | `""` | — |
| [chg\_typ](chg_typ.md) | Change type (`absval`, `abschg`, or `pctchg`; first entry echoed to `hru-new.cal`) | string | — | `""` | — |
| [neg](neg.md) | Negative change limit (parsed but unused) | real | — | 0 | — |
| [pos](pos.md) | Positive change limit (parsed but unused) | real | — | 0 | — |
| [lo](lo.md) | Lower parameter bound (parsed but unused) | real | — | 0 | — |
| [up](up.md) | Upper parameter bound (parsed but unused) | real | — | 0 | — |

In SWAT+ main (`6f515368`), only the first parameter row's `name` and `chg_typ` are written out to `hru-new.cal` at [`calsoft_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_control.f90#L159), and no routine adjusts `chcal%ord%prm%erod`.
