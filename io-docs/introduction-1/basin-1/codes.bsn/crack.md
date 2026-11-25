---
description: Crack flow code
---

# crack

**Code reference:** `bsn_cc%crk` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L25), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_cc.f90#L24)).

Enables or disables soil crack-volume and crack-flow calculations in [`hru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L303), [`surface.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/surface.f90#L53), and [`swr_percmain.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/swr_percmain.f90#L80) (struct default `0`).

| Code | Option |
| ---- | ------ |
| 0 | Do not compute crack flow in soil |
| 1 | Compute crack flow in soil |

If `crack = 1`, the crack volume potential is controlled by [perc\_crk](../../soils/soils.sol/perc_crk.md) in [**soils.sol**](../../soils/soils.sol/).
