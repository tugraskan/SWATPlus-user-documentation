---
description: Control switches that enable or disable soft-calibration procedures in SWAT+.
---

# codes.sft

Control flags for soft calibration, read sequentially into `cal_codes` ([`calibration_data_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L66)) by [`calsoft_read_codes.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_read_codes.f90#L29-L45).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [hyd\_hru](hyd_hru.md) | HRU water balance soft-calibration mode (`n`, `a`, `b`, or `y`) | string | — | `n` | `n`, `a`, `b`, `y` |
| [hyd\_hrulte](hyd_hrulte.md) | HRU-LTE water balance soft-calibration switch | string | — | `n` | `y`, `n` |
| [plt](plt.md) | Plant growth soft-calibration switch | string | — | `n` | `y`, `n` |
| [sed](sed.md) | Land-phase sediment soft-calibration switch | string | — | `n` | `y`, `n` |
| [nut](nut.md) | Land-phase nutrient soft-calibration flag (calibration routine not implemented) | string | — | `n` | `y`, `n` |
| [chsed](chsed.md) | Channel sediment soft-calibration flag (output accumulation and `hru-new.cal` write only) | string | — | `n` | `y`, `n` |
| [chnut](chnut.md) | Channel nutrient soft-calibration flag (calibration routine not implemented) | string | — | `n` | `y`, `n` |
| [res](res.md) | Reservoir soft-calibration flag (calibration routine not implemented) | string | — | `n` | `y`, `n` |

In SWAT+ main (`6f515368`), setting `hyd_hru /= "n"` or setting any of the remaining seven flags (`hyd_hrulte`, `plt`, `sed`, `nut`, `chsed`, `chnut`, `res`) to `"y"` sets the global gate `cal_soft = "y"` in [`calsoft_read_codes.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_read_codes.f90#L39), even when a specific flag's calibration routine is unimplemented.
