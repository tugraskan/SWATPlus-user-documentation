---
description: Saturated hydraulic conductivity of the soil layer
---

# soil\_k

**Code reference:** `soildb(isol)%ly(j)%k` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_data_module.f90#L50)).

Saturated hydraulic conductivity of the soil layer (`mm/hr`; Fortran struct default: `10.0`), relating soil water flux density to hydraulic gradient. When `soil_k <= 0.0`, [`soil_phys_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_phys_init.f90#L57-L72) assigns a fallback based on [`hyd_grp`](hyd_grp.md): `50.0` (A), `20.0` (B), `5.0` (C), `2.0` (D), or `10.0` mm/hr otherwise.

SWAT+ uses $K_{\text{sat},l}$ to compute the percolation travel time $t_{\text{perc},l}$ (hr, floored at 1 hr during initialization in [`soil_phys_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_phys_init.f90#L153-L155) and updated in [`swr_percmicro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/swr_percmicro.f90#L75)) and lateral subsurface flow ([`swr_percmicro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/swr_percmicro.f90#L69)):

$$t_{\text{perc},l} = \frac{\text{UL}_l - \text{FC}_l}{K_{\text{sat},l}}, \qquad Q_{\text{lat},l} = 0.024 \cdot f_{\text{lat}} \cdot h_o \cdot K_{\text{sat},l} \cdot \frac{S}{L_{\text{lat}}}$$

where $\text{UL}_{l}$ and $\text{FC}_{l}$ are saturation and field-capacity storage above wilting point (mm), $f_{\text{lat}}$ is `latq_co`, $h_o$ is drainable water depth (mm), $S$ is slope, and $L_{\text{lat}}$ is lateral flow length (m). Surface-layer `soil_k` also enters Green-Ampt infiltration ([`sq_greenampt.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sq_greenampt.f90#L95)), filter-strip trapping ([`smp_filter.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/smp_filter.f90#L112)), tile drainage ([`swr_drains.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/swr_drains.f90#L119)), and wetland bottom conductivity fallback ([`wet_read_hyd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_read_hyd.f90#L63)).
