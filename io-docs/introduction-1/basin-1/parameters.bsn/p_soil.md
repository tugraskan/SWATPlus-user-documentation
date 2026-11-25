---
description: Phosphorus soil partitioning coefficient
---

# p\_soil

**Code reference:** `bsn_prm%phoskd` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L96), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L24)).

Ratio of soluble phosphorus concentration in the top soil layer to its concentration in surface runoff ($k_d$, `m^3/Mg`, default `175`, range `100–200`; values `< 1.e-6` are reset to `175.0` in [`basin_prm_default.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_prm_default.f90#L21) and copied per HRU in [`hrudb_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hrudb_init.f90#L30)).

In [`nut_solp.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/nut_solp.f90#L66-L67), soluble phosphorus lost in surface runoff (`kg/ha`) is computed as:

$$P_{\text{surq}} = \frac{P_{\text{lab},1}\,Q_{\text{surf}}}{\rho_{b,1}\,z_1\,k_d + 1}$$

where $P_{\text{lab},1}$ is top-layer labile P (`kg/ha`), $Q_{\text{surf}}$ is surface runoff (`mm`), $\rho_{b,1}$ is top-layer bulk density (`Mg/m^3`), and $z_1$ is top-layer thickness (`mm`).
