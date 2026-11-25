---
description: Delivery ratio name or calculation keyword for the element
---

# dlr

**Code reference:** `ru_elem(i)%dr_name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L496)).

The `dlr` field specifies how the organic/mineral delivery ratio (`ru_elem(i)%dr`) is determined for the Routing Unit element:

* **Named record:** Matched against [name](../delratio.del/name.md) in [**delratio.del**](../delratio.del/) during [`ru_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_read_elements.f90#L76-L82) (and [`hru_fr_change.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_fr_change.f90#L53-L59)), copying the linked organic/mineral record from [**dr\_om.del**](../dr_om.del/) (`ru_elem(i)%dr = dr(dr_om_num(idr))`; note that the lookup loop upper bound is `db_mx%dr_om`). Constituent delivery ratios are not applied to Routing Unit elements in [`ru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_control.f90#L124-L132).
* **`full` or `1`:** Sets all organic/mineral delivery ratios to `1.0` in [`dr_ru.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_ru.f90#L36-L38).
* **`calc` or `0`:** Computes a time-of-concentration delivery ratio in [`dr_ru.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_ru.f90#L20-L35):

$$r_{\text{dr}} = \min\!\left(1.0,\; \sqrt{\frac{t_{c,\text{elem}}}{t_{c,\text{ru}}}}\right)$$

where $t_{c,\text{elem}}$ (`hr`) is `tconc(ihru)` for `hru` elements and `hlt_db(ihru)%tc / 3600.` for `hlt` elements (with $t_{c,\text{elem}} / t_{c,\text{ru}}$ set directly to `1.0` for `sdc` and `ru` elements), and $t_{c,\text{ru}}$ is `ru_tc(iru)` (`hr`). The ratio $r_{\text{dr}}$ is assigned to all organic/mineral components except water flow, which is forced to `1.0` ([`dr_ru.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_ru.f90#L34)).

In [`ru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_control.f90#L96-L147), `ru_elem(ise)%dr` multiplies `exc` export-coefficient hydrographs and hydrograph types `1` (total), `3` (surface), `4` (lateral), and `5` (tile), but is not applied to type `2` (recharge, [`ru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_control.f90#L121-L135)). Any unrecognized keyword or missing name leaves `ru_elem(i)%dr` at its Fortran default (`0.0`), zeroing out routed organic/mineral loads.
