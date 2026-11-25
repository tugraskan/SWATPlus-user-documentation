---
description: Fraction of the curb length that is sweepable
---

# frac\_curb

**Code reference:** `sweepop_db(isweepop)%fr_curb` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L137), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_sweepops.f90#L47)).

Dimensionless availability factor (`fraction`; default `0.0`, valid range `0.0–1.0`) representing the fraction of urban curb length accessible for street sweeping rather than blocked by parked vehicles or other obstacles. In [`hru_sweep.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_sweep.f90#L45), it is intended to multiply `swp_eff`:

$$D_{\text{new}} = D \cdot (1 - f_{\text{curb}} \cdot E_{\text{swp}})$$

where $D_{\text{new}}$ is solids remaining after sweeping (`kg/curb km`), $D$ is solids built up on impervious surfaces (`kg/curb km`), $f_{\text{curb}}$ is `frac_curb` (dimensionless), and $E_{\text{swp}}$ is `swp_eff` (dimensionless).

*(Note: In SWAT+ main (6f515368), [`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L48) [`#L482`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L482) copies `sweepop%fr_curb` into a local variable, while [`hru_sweep.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_sweep.f90#L34) [`#L45`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_sweep.f90#L45) evaluates its own local `fr_curb = 0.`, so this parameter has no active effect on urban buildup removal).*
