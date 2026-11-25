---
description: Peak rate factor for the NRCS dimensionless-hydrograph peak-runoff equation
---

# adj\_pkrt\_sed

**Code reference:** `bsn_prm%prf` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L84), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L24)).

Peak rate factor ($c_{\text{prf}}$) used when the NRCS dimensionless-hydrograph method ([sed\_det](../codes.bsn/sed_det.md) = `0`) computes HRU peak runoff rate (`m^3/s`) in [`ero_pkq.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ero_pkq.f90#L52-L53) and wetland overland inflow peak rate in [`wetland_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wetland_control.f90#L230):

$$q_p = \frac{c_{\text{prf}}}{6578.6 \times 35.3} \cdot \frac{A_{\text{ha}}\,Q_{\text{day}}}{t_c}$$

where $A_{\text{ha}}$ is HRU area (`ha`), $Q_{\text{day}}$ is daily surface runoff (`mm`), and $t_c$ is time of concentration (`hr`). While the Fortran struct initializes `prf = 484.`, [`basin_prm_default.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_prm_default.f90#L13) resets values `< 1.e-6` to `1.0` (matching the historical table default `1`, range `0–2`). It is not a main-channel sediment-routing factor in SWAT+ main (`6f515368`).
