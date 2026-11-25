---
description: "Pathogen concentration of treated water"
---

# path

**Code reference:** `wtp_cs_treat(iwtp)%path` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L1), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_treatment_read.f90#L109-L113)).

Pathogen concentration of treated water (`cfu`, array length `cs_db%num_paths`). Read inside the `itrt` loop after a header line when `cs_db%num_paths > 0` ([`water_treatment_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_treatment_read.f90#L109-L113)). Converted to mass in [`wallo_treatment.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_treatment.f90#L83) via [`constituent_mass_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L719-L721):

$$M = \frac{Q_{\text{out}} \cdot C}{1000}$$

where $Q_{\text{out}}$ is treated POR outflow `outflo_om%flo` (`m^3`) and $C$ is `path`.
