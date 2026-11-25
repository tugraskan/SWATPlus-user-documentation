---
description: This file contains pre-defined street sweeping operations.
---

# sweep.ops

This file defines pre-defined urban street sweeping operations read by [`mgt_read_sweepops.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_sweepops.f90#L27-L54).

In SWAT+ main (`6f515368`), `sweep.ops` entries are parsed and matched for `swep` operations in `management.sch` ([`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L480-L482)), but street sweeping does not actively reduce urban solids: [`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L48) assigns `fr_curb` to a local variable without calling [`hru_sweep.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_sweep.f90#L34-L45), where a separate local `fr_curb = 0.` keeps `1. - fr_curb * sweepeff` equal to `1.`.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name_sweep.md) | Street sweeping operation name | string | n/a | n/a | n/a |
| [swp\_eff](swp_eff.md) | Removal efficiency of sweeping operation | real | fraction | 0.0 | 0.0-1.0 |
| [frac\_curb](frac_curb.md) | Fraction of the curb length that is sweepable | real | fraction | 0.0 | 0.0-1.0 |
