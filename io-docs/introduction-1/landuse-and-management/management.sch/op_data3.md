---
description: Operation data 3 (op3)
---

# op\_data3

**Code reference:** `sched(isched)%mgt_ops(iop)%op3` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L169), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/read_mgtops.f90#L33)).

Real numeric parameter (default `0.0`) providing operation-specific rates, thresholds, or flags in [`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L101-L561).

| Operation | Use of `op_data3` |
| --------- | ----------------- |
| `plnt` | Flag `> 1e-6` enables transplanting using [op\_data2](op_data2.md) ([`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L101-L110)) |
| `mons` | Monsoon season switch: `1` starts the moisture-triggered season (`mseas = "y"`), `0` ends it and resets phenology if not growing ([`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L141-L150)) |
| `harv`, `hvkl` | Residue harvest efficiency (`0.0–1.0`) passed to `mgt_harvresidue` when `harv.ops` `typ == "residue"` ([`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L172), [`#L230`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L230), [`#L284`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L284), [`#L337`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L337)) |
| `fert`, `manu`, `pest` | Application rate (`kg/ha`); for `pest`, multiplied by `chem_app.ops` `app_eff` ([`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L378), [`#L405`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L405), [`#L430`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L430)) |
| `graz` | Grazing duration in days (`Int(op3)`) ([`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L443)) |
| `cnup` | Curve number adjustment value passed to `chg_par` and clamped to `35.0–95.0` ([`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L457)) |
| `dwm` | Tile drain depth (`mm`); `<= 0` disables drainage (`ldrain = 0`) ([`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L491-L500)) |
| `weir` | Weir height (`mm`), divided by `1000` to set `wet_ob(j)%weir_hgt` (`m`) and principal spillway volume ([`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L511-L515)) |
| `irrp` | Target paddy ponding depth (`mm`): `> 0` enables paddy irrigation and sets maximum and minimum ponding targets (see below), `0` turns paddy irrigation off, and `< 0` uses `irr.ops` `amt_mm` (line `530` also copies `op3` to `irr_isc`) ([`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L531-L561)) |
| All other operations | Not used (enter `0.0`) |

For `irrp` when `op_data3 > 0`, SWAT+ sets the target paddy ponding depths in [`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L538-L539) as:

$$h_{\max} = \text{op}_3, \qquad h_{\min} = 0.9\,h_{\max}$$

where $h_{\max}$ is the maximum target ponding depth (`irr_hmax`, `mm`), $\text{op}_{3}$ is `op_data3` (`mm`), and $h_{\min}$ is the minimum ponding depth trigger (`irr_hmin`, `mm`).
