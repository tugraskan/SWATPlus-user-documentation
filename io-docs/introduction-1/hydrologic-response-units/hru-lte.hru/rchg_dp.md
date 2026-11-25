---
description: Percolation coefficient from shallow to deep aquifer
---

# rchg\_dp

**Code reference:** `hlt_db(i)%percc` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_module.f90#L24)).

Fraction of the day's soil percolation that moves from the shallow aquifer to the deep aquifer, limited to the shallow storage remaining ([`hru_lte_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_control.f90#L335), [`hru_lte_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_control.f90#L343-L346)):

$$w_{deep} = w_{perc} \times f$$

where $w_{deep}$ is daily percolation to the deep aquifer (`mm`), $w_{perc}$ is daily soil percolation (`mm`), and $f$ is `rchg_dp` (fraction).
