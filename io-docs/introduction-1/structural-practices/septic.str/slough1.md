---
description: Linear coefficient for calculating the rate of biomass sloughing
---

# slough1

**Code reference:** `sep(isep)%slg1` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/septic_data_module.f90#L42)).

Linear coefficient used with [`slough2`](slough2.md) to calculate percolation-driven biomass sloughing from the biozone ([`sep_biozone.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sep_biozone.f90#L214)):

$$R_{\text{slg}} = s_1 \cdot q_{\text{perc}}^{s_2} \cdot B$$

where $R_{\text{slg}}$ is daily sloughed biomass (kg/ha), $s_1$ is `slough1`, $s_2$ is `slough2`, $q_{\text{perc}}$ is biozone percolation (mm/day), and $B$ is live biomass (kg/ha).
