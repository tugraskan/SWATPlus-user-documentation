---
description: Parameter for frozen soil adjustment on infiltration/runoff
---

# cn\_froz

**Code reference:** `bsn_prm%cn_froz` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L115), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L24)).

Frozen-soil retention coefficient ($c_{\text{froz}}$, default `0.000862`; values `< 1.e-6` are reset to `0.000862` in [`basin_prm_default.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_prm_default.f90#L37)).

When the temperature of the second soil layer is at or below freezing ($T_{s,2} \le 0\,^\circ\text{C}$), [`sq_dailycn.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sq_dailycn.f90#L52) and [`sq_greenampt.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sq_greenampt.f90#L171) reduce the Curve Number retention parameter $S$ (`mm`) from its soil-water-adjusted value toward lower infiltration capacity:

$$S_{\text{froz}} = S_{\max}\left(1 - \exp\!\left(-c_{\text{froz}}\,S\right)\right)$$

where $S_{\max}$ is the maximum Curve Number retention parameter (`mm`).
