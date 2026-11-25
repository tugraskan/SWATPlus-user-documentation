---
description: Residue-cover coefficient used in the C-factor calculation
---

# rsd\_cover

**Code reference:** `bsn_prm%rsd_covco` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L121), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L24)).

Exponential residue-cover coefficient ($c_{\text{rsd}}$, struct default `0.75`, runtime fallback `0.75` when `< 1.e-6` in [`basin_prm_default.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_prm_default.f90#L41); exposed to calibration in [`cal_parm_select.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L465)).

Used in the APEX residue/biomass USLE C-factor calculation in [`ero_cfactor.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/ero_cfactor.f90#L68-L77):

$$f_{\text{rsd}} = \exp\!\left(-c_{\text{rsd}} \cdot \frac{M_{\text{rsd}} + 1}{1000}\right), \qquad C = \max\!\left(10^{-10},\; f_{\text{rsd}} \cdot f_{\text{bio}}\right)$$

where $M_{\text{rsd}}$ is total residue mass (`kg/ha`) and $f_{\text{bio}}$ is the growing biomass cover factor.
