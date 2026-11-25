---
description: Pointer to the topography file
---

# topo

**Code reference:** `ru(i)%dbsc%toposub_db` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_module.f90#L14)).

The pointer to the topography file is a foreign key referencing [name](../../hydrology/topography.hyd/name.md) in [**topography.hyd**](../../hydrology/topography.hyd/). During input parsing in [`ru_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_read.f90#L233-L239), the name is matched against `topo_db(:)%name` and stored in `ru(i)%dbs%toposub_db` (Fortran struct default `1` in [`ru_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_module.f90#L21) if unmatched).

The matched topography parameters (`slope_len` and `slope`) are used in [`time_conc_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_conc_init.f90#L42-L51) to compute the Routing Unit time of concentration $t_{c,\text{ru}}$ (`hr`):

$$t_{\text{ov}} = \frac{0.0556\,(L_{\text{slp}}\,\bar{n})^{0.6}}{(S + 0.001)^{0.3}}, \qquad t_{\text{ch}} = \frac{0.62\,L_{\text{ch}}\,\bar{n}^{0.75}}{A^{0.125}\,(0.5\,(S + 0.001))^{0.375}}, \qquad t_{c,\text{ru}} = t_{\text{ov}} + t_{\text{ch}}$$

where $L_{\text{slp}}$ is `topo_db(ith)%slope_len` (`m`), $S$ is `topo_db(ith)%slope` (`m/m`), $\bar{n}$ is the area-weighted Manning's $n$ (`ru_n(iru)`), $L_{\text{ch}}$ is `ru(iru)%field%length / 1000` (`km`), and $A$ is the Routing Unit drainage area `ru(iru)%da_km2` (`km^2`).

The resulting `ru_tc(iru)` is used in [`dr_ru.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_ru.f90#L23-L25) for `calc`/`0` element delivery ratios and in [`unit_hyd_ru_hru.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/unit_hyd_ru_hru.f90#L27) for sub-daily unit hydrographs. When sub-daily Green & Ampt routing is active, [`ru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_control.f90#L253) overwrites `ru_tc(iru) = 2.` `hr` during hydrograph translation.
