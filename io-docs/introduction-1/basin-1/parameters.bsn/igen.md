---
description: Random-number generator seed code
---

# igen

**Code reference:** `bsn_prm%igen` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L134), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L24)).

Integer control code for random-number generator initialization in [`gcycl.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gcycl.f90#L82-L109) (struct default `5`):

* `igen = 0`: Uses the fixed default seed array (`rndseed`) for reproducible weather-generator runs.
* `igen /= 0`: Advances the auxiliary seed `rndseed10` by $\lfloor 100 \cdot \text{igen} \cdot r_n \rfloor$ steps for each of the 9 seeds, updates `rndseed(:,1)` and the decision-table seed `rndseed_cond`, and shuffles the seed permutation `idg(1:9)`.
