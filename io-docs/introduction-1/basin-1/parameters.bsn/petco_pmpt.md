---
description: PET adjustment for Penman-Monteith and Priestley-Taylor methods (read but not used in main 6f515368)
---

# petco\_pmpt

**Code reference:** `bsn_prm%petco_pmpt` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L123), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L24)).

Percentage PET adjustment placeholder for Penman-Monteith and Priestley-Taylor methods (struct default `100.0`). In [`basin_prm_default.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_prm_default.f90#L43-L44), values in `(0, 0.5)` are reset to `0.0` and `bsn_prm%petco_pmpt` is converted via `(100. + petco_pmpt) / 100.`, but the converted value is never read by [`et_pot.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/et_pot.f90#L115-L280) or any other routine.

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
