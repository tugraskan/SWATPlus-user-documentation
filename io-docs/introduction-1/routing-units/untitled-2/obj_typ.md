---
description: Object type of the element
---

# obj\_typ

**Code reference:** `ru_elem(i)%obtyp` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L493)).

The following 3-character object type codes are recognized by [`ru_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_read_elements.f90#L143-L162) for elements in a Routing Unit:

* `hru` — HRU
* `hlt` — HRU-LTE
* `ru` — routing unit
* `cha` — channel
* `res` — reservoir
* `exc` — export coefficient
* `dr` — delivery-ratio object
* `out` — outlet
* `sdc` — SWAT-degenerate channel

Downstream routines also dispatch on `obtyp`: [`time_conc_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_conc_init.f90#L29) uses `hru` elements to compute area-weighted Manning's $n$, [`dr_ru.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_ru.f90#L21-L30) selects calculated delivery ratios for `hru`, `hlt`, `sdc`, and `ru`, and [`ru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_control.f90#L98-L117) handles `exc` export coefficients separately from other objects (and processes `hru` elements for [sub-daily](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_control.f90#L231) Green & Ampt runoff).
