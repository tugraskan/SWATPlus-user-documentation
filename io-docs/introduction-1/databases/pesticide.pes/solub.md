---
description: Solubility of the pesticide in water
---

# solub

**Code reference:** `pestdb(ip)%solub` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pesticide_data_module.f90#L11)).

**Current use:** caps the pesticide concentration in water leaving a soil layer ([`pest_lch.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_lch.f90#L58)) and the dissolved mass in a channel ([`ch_rtpest.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_rtpest.f90#L202-L206)).

The water solubility value defines the highest concentration of pesticide that can be reached in the runoff and soil pore water. While this is an important characteristic, researchers have found that the soil adsorption coefficient, $K_{\text{oc}}$, tends to limit the amount of pesticide entering solution so that the maximum possible concentration of pesticide in solution is seldom reached. Reported solubility values are determined under laboratory conditions at a constant temperature, typically between 20°C and 30°C.
