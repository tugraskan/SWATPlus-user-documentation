---
description: Clay content of the soil layer
---

# clay

**Code reference:** `soildb(isol)%ly(j)%clay` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_data_module.f90#L52)).

Percent by weight of soil particles that are `< 0.002` mm in equivalent diameter (`%`; Fortran struct default: `10.0`). In [`soil_phys_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_phys_init.f90#L91-L92), `clay` estimates each layer's wilting-point water content:

$$\theta_{\text{wp},l} = \max\!\left(0.005,\; \frac{0.4 \cdot \text{clay}_l \cdot \rho_{b,l}}{100}\right)$$

where $\rho_{b,l}$ is layer bulk density ($\text{Mg/m}^3$). Surface-layer clay also sets detached sediment fractions ([`soil_phys_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_phys_init.f90#L109-L122)), Green-Ampt wetting-front suction head ([`soils_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soils_init.f90#L295)), surface sand recalculation ([`soil_phys_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_phys_init.f90#L179)), dynamic phosphorus sorption ([`nut_pminrl2.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/nut_pminrl2.f90#L60)), and CENTURY carbon allocation ([`cbn_zhang2.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cbn_zhang2.f90#L467-L498)).
