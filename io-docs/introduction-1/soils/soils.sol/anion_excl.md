---
description: Fraction of porosity (void space) from which anions are excluded
---

# anion\_excl

**Code reference:** `soildb(isol)%s%anion_excl` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_data_module.f90#L68)).

Most soil minerals are negatively charged at normal pH and the net interaction with anions such as nitrate is a repulsion from particle surfaces. This repulsion is termed negative adsorption or anion exclusion. Anions are excluded from the area immediately adjacent to mineral surfaces due to preferential attraction of cations to these sites. This process has a direct impact on the transport of anions through the soil for it effectively excludes anions from the slowest moving portion of the soil water volume found closest to the charged particle surfaces (Jury et al., 1991). In effect, the net pathway of the anion through the soil is shorter than it would be if all the soil water had to be used (Thomas and McMahon, 1972).

Expressed as a dimensionless `fraction` in `(0, 1)` (Fortran struct default: `0.5`), values are clamped during initialization in [`soil_phys_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_phys_init.f90#L52-L53): values $\le 10^{-6}$ are reset to `0.5`, and values $\ge 1$ are capped at `0.99`. In solute leaching ([`nut_nlch.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/nut_nlch.f90#L84), [`salt_lch.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_lch.f90#L120), [`cs_lch.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_lch.f90#L98)), `anion_excl` reduces the effective pore water volume in the mobile-water exponent:

$$w = \frac{-v_{\text{mob}}}{(1 - \theta_{\text{an}}) \cdot \text{UL}}$$

where $v_{\text{mob}}$ is mobile water leaving the layer (mm), $\theta_{\text{an}}$ is `anion_excl` (fraction), and $\text{UL}$ is the layer saturated water capacity above wilting point (mm).

#### References

> Jury et al., 1991
>
> Thomas and McMahon, 1972
