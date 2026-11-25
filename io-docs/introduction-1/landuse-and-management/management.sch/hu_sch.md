---
description: Heat-unit scheduling threshold fraction
---

# hu\_sch

**Code reference:** `sched(isched)%mgt_ops(iop)%husc` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L164), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/read_mgtops.f90#L30)).

Dimensionless fraction of accumulated heat units (default `0.0`) used to schedule an operation instead of—or in addition to—a calendar date. In [`mgt_operatn.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operatn.f90#L64-L85), an operation fires whenever `husc > 0` and $\text{aphu} > \text{husc}$, where $\text{aphu}$ is base-zero accumulated heat units `phubase(j)` when the plant is not growing (`gro == "n"`), or the plant's accumulated heat-unit fraction `pcom(j)%plcur(ipl)%phuacc` when growing (`gro == "y"`).
