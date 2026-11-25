---
description: Linear P sorption distribution coefficient
---

# p\_sorp

**Code reference:** `sep(isep)%pdistrb` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/septic_data_module.f90#L46)).

Linear phosphorus sorption distribution coefficient (L/kg) used with [`p_sorp_max`](p_sorp_max.md) in [`sep_biozone.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sep_biozone.f90#L275) to calculate P sorption per unit mass of sub-biozone soil:

$$S_p = \min(K_d \cdot C_p,\; S_{\text{max}})$$

where $S_p$ is sorbed P per unit soil mass (mg P/kg soil), $K_d$ is `p_sorp` (L/kg), $C_p$ is labile P concentration in biozone water (mg/L), and $S_{\text{max}}$ is `p_sorp_max` (mg P/kg soil).
