---
description: Peak runoff rate method
---

# sed\_det

**Code reference:** `bsn_cc%sed_det` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L30), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_cc.f90#L24)).

Selects the method used to calculate HRU peak runoff rate in [`ero_pkq.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ero_pkq.f90#L43-L54) (struct default `0`).

| Code | Option |
| ---- | ------ |
| 0 | NRCS dimensionless hydrograph with peak rate factor |
| 1 | Half-hour rainfall intensity method |

When `sed_det = 0`, peak runoff rate uses [adj\_pkrt\_sed](../parameters.bsn/adj_pkrt_sed.md) ($c_{\text{prf}}$):

$$q_p = \frac{c_{\text{prf}}}{6578.6 \times 35.3} \cdot \frac{A_{\text{ha}}\,Q_{\text{day}}}{t_c}$$

where:
- $q_p$ is the peak runoff rate (`m^3/s`),
- $c_{\text{prf}}$ is `adj_pkrt_sed` (dimensionless),
- $A_{\text{ha}}$ is the HRU area (`ha`),
- $Q_{\text{day}}$ is daily surface runoff (`mm`), and
- $t_c$ is the HRU time of concentration (`hr`).

When `sed_det = 1`, peak runoff rate uses the half-hour rainfall fraction ($\alpha_{0.5}$):

$$\alpha_{tc} = 1 - \exp\!\left(2\,t_c\,\ln(1 - \alpha_{0.5})\right), \qquad q_p = \frac{\alpha_{tc}\,Q_{\text{day}}\,A_{\text{km}}}{3.6\,t_c}$$

where:
- $\alpha_{tc}$ is the fraction of daily rainfall falling within the time of concentration (dimensionless),
- $t_c$ is the HRU time of concentration (`hr`),
- $\alpha_{0.5}$ is the maximum half-hour rainfall fraction (dimensionless),
- $q_p$ is the peak runoff rate (`m^3/s`),
- $Q_{\text{day}}$ is daily surface runoff (`mm`), and
- $A_{\text{km}}$ is the HRU area (`km^2`).
