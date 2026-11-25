---
description: Maximum daily nitrogen fixation
---

# n\_fix\_max

**Code reference:** `bsn_prm%nfixmx` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L119), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L24)).

Maximum daily symbiotic nitrogen fixation allowed for nitrogen-fixing plants (`kg N/ha/day`, default `20`, range `1–20`; values `< 1.e-6` are reset to `20.0` in [`basin_prm_default.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_prm_default.f90#L39)).

In [`pl_nfix.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_nfix.f90#L87), daily fixed nitrogen is capped at `n_fix_max`:

$$\text{fix}_{N} = \min\!\big(\text{nfixmx},\; \text{fix}_{N}\big)$$

where $\text{fix}_{N}$ is daily fixed nitrogen (`kg N/ha/day`) and $\text{nfixmx}$ is `n_fix_max` (`kg N/ha/day`).
