---
description: "Pesticide concentration of treated water"
---

# pest

**Code reference:** `wtp_cs_treat(iwtp)%pest` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L1), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_treatment_read.f90#L102-L106)).

Pesticide concentration of treated water (`ppm`, array length `cs_db%num_pests`). Read inside the `itrt` loop after a header line when `cs_db%num_pests > 0` ([`water_treatment_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_treatment_read.f90#L102-L106)). Converted to mass in [`wallo_treatment.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_treatment.f90#L83) via [`constituent_mass_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L716-L718):

$$M = \frac{Q_{\text{out}} \cdot C}{1000}$$

where $Q_{\text{out}}$ is treated POR outflow `outflo_om%flo` (`m^3`) and $C$ is `pest`.
