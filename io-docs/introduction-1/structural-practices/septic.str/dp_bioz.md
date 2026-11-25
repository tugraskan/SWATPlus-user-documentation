---
description: Depth to the top of the biozone layer from the ground surface
---

# dp\_bioz

**Code reference:** `sep(isep)%z` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/septic_data_module.f90#L28)).

The depth (mm) includes the top soil layer and septic tank effluent (STE) distribution chamber, including perforated pipe. During soil initialization ([`soils_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soils_init.f90#L323-L339)), soil layers are adjusted around `dp_bioz` and `dp_bioz + thk_bioz` to represent the biozone layer.

In [`sep_biozone.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sep_biozone.f90#L271), `dp_bioz` also sets the sub-biozone soil volume ($V_p$, $\text{m}^3$) available for phosphorus sorption:

$$V_p = (z_{\text{max}} - z_{\text{bz}}) \cdot A_{\text{hru}} \cdot 10$$

where $z_{\text{max}}$ is total soil profile depth (mm), $z_{\text{bz}}$ is `dp_bioz` (mm), and $A_{\text{hru}}$ is HRU area (ha).
