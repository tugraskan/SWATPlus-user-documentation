---
description: Fraction of Landscape Unit area assigned to this element
---

# ru\_frac

**Code reference:** `lsu_elem(i)%ru_frac` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L225), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lsu_read_elements.f90#L127)).

Dimensionless expansion fraction representing this element's share of its parent Landscape Unit area (`real`, `fraction`, typical range `0.0-1.0`, default `0.0`; typically sums to `1.0` per Landscape Unit). Older SWAT+ Editor files may label this positional column `sub_frac`.

For elements with $f_{\text{ru}} > 10^{-9}$, SWAT+ weights HRU and HRU-LTE states and fluxes into Landscape Unit totals ([`lsu_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lsu_output.f90#L37-L53), [`lsu_carbon_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lsu_carbon_output.f90#L48-L50), [`basin_sw_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_sw_init.f90#L69-L78)):

$$X_{\text{lsu}} = \sum_{e \in \text{lsu}} X_{e} \cdot f_{\text{ru},e}$$

where $X_{e}$ is the element state or flux and $f_{\text{ru},e}$ is `ru_frac`.
