---
description: Fraction of element in Routing Unit
---

# frac

**Code reference:** `ru_elem(i)%frac` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L495)).

The fraction of an element in a Routing Unit acts as a weighting factor (Fortran struct default: `0`). In [`ru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_control.f90#L92-L147), each element's hydrograph contribution is multiplied by an expansion factor $e_{f}$:

**Scaled `hru`, `hlt`, and `exc` elements:** For `hru` and `hlt` elements with $\text{frac} < 0.99999$ ([`ru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_control.f90#L112-L116)), and for `exc` elements with $A_{\text{ob}} > 0.01$ `ha` ([`ru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_control.f90#L102-L105)), SWAT+ scales `frac` by the area ratio:

$$e_{f} = \text{frac} \cdot \frac{A_{\text{ru}}}{A_{\text{ob}} / 100}$$

where $e_{f}$ is the expansion factor (dimensionless), $\text{frac}$ is `ru_elem(i)%frac` (dimensionless), $A_{\text{ru}}$ is `ru(iru)%da_km2` (`km^2`), and $A_{\text{ob}}$ is `ob(iob)%area_ha` (`ha`).

**Other elements:** For all other object types, or for `hru` and `hlt` elements with $\text{frac} \ge 0.99999$ ([`ru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_control.f90#L110-L114)):

$$e_{f} = \text{frac}$$

where $e_{f}$ is the expansion factor (dimensionless) and $\text{frac}$ is `ru_elem(i)%frac` (dimensionless).

Each element's routed hydrograph is multiplied by $e_{f}$ ([`ru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_control.f90#L105), [multiply](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_control.f90#L147)). `frac` also enters sub-daily Green & Ampt conversion ([`ru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_control.f90#L235)), overland incoming-fraction calculation for objects routed onto a Routing Unit ([`hyd_connect.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hyd_connect.f90#L397)), and snowmelt weighting in stream temperature modeling ([`ch_temp.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_temp.f90#L222-L224)).

{% hint style="danger" %}
The model accumulates `sumfrac` ([`ru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_control.f90#L92)) without validating or normalizing the `frac` values. If they do not sum appropriately for a Routing Unit, the routed water and constituent scaling will reflect that directly.
{% endhint %}
