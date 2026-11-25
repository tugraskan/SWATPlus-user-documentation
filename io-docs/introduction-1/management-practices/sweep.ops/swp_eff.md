---
description: Removal efficiency of sweeping operation
---

# swp\_eff

**Code reference:** `sweepop_db(isweepop)%eff` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L136), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_sweepops.f90#L47)).

Dimensionless removal efficiency (`fraction`; default `0.0`, valid range `0.0–1.0`) of the street sweeping operation. Removal efficiency depends on sweeper type, street flushing, total solids load, rainfall frequency, and target constituents; particulate removal is typically higher than nutrient removal, though SWAT+ assumes fixed nutrient concentrations in solids so the same efficiency applies across constituents (Pitt, 1979).

In [`hru_sweep.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_sweep.f90#L45), street sweeping is formulated as:

$$D_{\text{new}} = D \cdot (1 - f_{\text{curb}} \cdot E_{\text{swp}})$$

where $D$ is solids built up on impervious surfaces (`kg/curb km`), $f_{\text{curb}}$ is `frac_curb`, and $E_{\text{swp}}$ is `swp_eff`.

*(Note: In SWAT+ main (6f515368), [`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L481) copies `swp_eff` to module variable `sweepeff` in [`hru_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_module.f90#L396), [`hru_sweep.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_sweep.f90#L45) is called only from subdaily urban runoff in [`hru_urbanhr.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_urbanhr.f90#L130-L158), and because [`hru_sweep.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_sweep.f90#L34) uses a local `fr_curb = 0.`, the product $f_{\text{curb}} \cdot E_{\text{swp}}$ always evaluates to `0.`).*

#### References

> Pitt (1979)
