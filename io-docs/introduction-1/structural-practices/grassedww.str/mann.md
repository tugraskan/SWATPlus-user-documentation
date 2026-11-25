---
description: Manning's n for grassed waterway
---

# mann

**Code reference:** `grwaterway_db(igrwwop)%grwat_n` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L50)).

Manning's roughness coefficient $n$ for the grassed waterway (dimensionless; range `0.001–0.50`). It is used in Manning's equation ([`qman.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/qman.f90#L21)) for waterway flow rate and velocity, and in [`structure_set_parms.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/structure_set_parms.f90#L94) for waterway time of concentration:

$$Q = \frac{A \, R_h^{2/3} \, S^{1/2}}{n + 0.001}, \qquad t_{\text{ch}} = \frac{0.62 \, L \, n^{0.6}}{A_{\text{km}}^{0.125} \, S^{0.375}}$$

where $Q$ is discharge ($\text{m}^3/\text{s}$), $A$ is cross-sectional flow area ($\text{m}^2$), $R_h$ is hydraulic radius (m), $S$ is waterway slope ([`slp`](slp.md), m/m), $n$ is `mann`, $t_{\text{ch}}$ is waterway time of concentration (hr), $L$ is waterway length ([`len`](len.md), km), and $A_{\text{km}}$ is HRU area ($\text{km}^2$). At runtime ([`structure_set_parms.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/structure_set_parms.f90#L81)), if `mann <= 0`, SWAT+ resets it to `0.35`.
