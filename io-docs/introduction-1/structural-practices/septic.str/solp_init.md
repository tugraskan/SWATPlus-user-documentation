---
description: Intercept of the linear effluent soluble P equation
---

# solp\_int

**Code reference:** `sep(isep)%solpintc` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/septic_data_module.f90#L49)).

Intercept of the linear effluent soluble P equation used with [`solp_slp`](solp_slp.md) in [`sep_biozone.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sep_biozone.f90#L282) when biozone labile P is below the total sub-biozone sorption capacity:

$$P_{\text{end}} = m_p \cdot P_{\text{tot}} + b_p$$

where $P_{\text{end}}$ is end-of-day biozone labile soluble P (kg/ha), $m_p$ is `solp_slp`, $P_{\text{tot}}$ is the sum of labile and active mineral P in the biozone layer (kg/ha), and $b_p$ is `solp_int`.
