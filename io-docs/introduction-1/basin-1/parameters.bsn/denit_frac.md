---
description: Denitrification threshold as a fraction of field capacity
---

# denit\_frac

**Code reference:** `bsn_prm%sdnco` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L112), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L24)).

Defines the soil-water fraction of field capacity above which denitrification occurs (default `1.3`; values `< 1.e-6` are reset to `1.30` in [`basin_prm_default.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_prm_default.f90#L34)). Because SWAT+ does not explicitly track redox status, anaerobic conditions in a soil layer are assumed whenever the water-to-field-capacity ratio satisfies $f_w \ge \text{sdnco}$ in [`nut_nminrl.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/nut_nminrl.f90#L198) and [`cbn_zhang2.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cbn_zhang2.f90#L438). When $f_w < \text{sdnco}$, denitrification is `0`.
