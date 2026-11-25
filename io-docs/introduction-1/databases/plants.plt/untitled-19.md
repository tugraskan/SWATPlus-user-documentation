---
description: Nitrogen fixation coefficient
---

# nfix\_co

**Code reference:** `pldb(ic)%nfix_co` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L36)).

Any value above `1e-6` turns fixation on and also removes nitrogen stress for the plant ([`pl_nup.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_nup.f90#L91-L107)). The coefficient $c$ blends fixation with the unmet nitrogen demand $D$ ([`pl_nfix.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_nfix.f90#L84-L87)):

$$N = c\,\min(6, f D) + (1 - c)\,D$$

where $N$ is the fixed nitrogen (`kg N/ha`), $c$ is `nfix_co` (dimensionless), $f$ is the combined growth-stage, water, and nitrate factor (dimensionless), and $D$ is the unmet plant nitrogen demand (`kg N/ha`). The result is capped at $D$ and at the basin maximum [n\_fix\_max](../../basin-1/parameters.bsn/n_fix_max.md).

The nitrogen fixation coefficient in the SWAT+ plant database is 0.5 for legumes and 0.0 for non-legumes.
