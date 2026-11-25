---
description: Maximum initial abstraction for urban areas
---

# urb\_init\_abst

**Code reference:** `bsn_prm%urb_init_abst` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L122), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L24)).

Maximum initial abstraction (`mm`, table default `5`, range `0–10`; struct default `1.`, values `< 1.e-6` reset to `0.` in [`basin_prm_default.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_prm_default.f90#L42)) for impervious surfaces in urban HRUs when using the Green & Ampt method ([gampt](../codes.bsn/gampt.md) = `1`).

In [`sq_greenampt.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sq_greenampt.f90#L137-L147), sub-daily dry-period impervious abstraction capacity recovers up to `urb_init_abst` at rate $\text{PET} / \text{step}$ and is depleted by rainfall before generating impervious urban runoff.
