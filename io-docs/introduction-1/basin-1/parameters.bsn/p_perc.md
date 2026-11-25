---
description: Phosphorus percolation coefficient
---

# p\_perc

**Code reference:** `bsn_prm%pperco` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L93), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L24)).

Phosphorus percolation coefficient ($\beta_P$, `10 m^3/Mg`, default `10`, range `10–17.5`; values `< 1.e-6` are reset to `10.0` in [`basin_prm_default.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_prm_default.f90#L19) and copied per HRU in [`hrudb_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hrudb_init.f90#L31)).

In [`nut_solp.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/nut_solp.f90#L69-L70) for soil-layer percolation and [`#L82-L83`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/nut_solp.f90#L94-L95) for tile drainage, leached labile phosphorus (`kg/ha`) is computed as:

$$P_{\text{lch}} = 0.001\,P_{\text{lab}}\left(1 - \exp\!\left(\frac{-Q}{0.01\,\text{SW}_{l} + 0.1\,\beta_P\,\rho_b}\right)\right)$$

where $P_{\text{lab}}$ is layer labile P (`kg/ha`), $Q$ is percolation or tile flow (`mm`), $\text{SW}_{l}$ is layer soil water (`mm`), and $\rho_b$ is soil bulk density (`Mg/m^3`).
