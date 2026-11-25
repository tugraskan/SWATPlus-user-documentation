---
description: Slope of grassed waterway
---

# slp

**Code reference:** `grwaterway_db(igrwwop)%grwat_s` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L55)).

Average slope of the grassed waterway in m/m (range `0.0–1.0`). It enters Manning's discharge equation ([`qman.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/qman.f90#L21)) as $S^{1/2}$ and the waterway time of concentration ([`structure_set_parms.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/structure_set_parms.f90#L94)) as $S^{-0.375}$.

At runtime ([`structure_set_parms.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/structure_set_parms.f90#L89)), if `slp <= 0`, SWAT+ sets it to 75% of the HRU topographic slope:

$$S = 0.75 \, S_{\text{hru}}$$

where $S$ is `slp` (m/m) and $S_{\text{hru}}$ is HRU slope (m/m).
