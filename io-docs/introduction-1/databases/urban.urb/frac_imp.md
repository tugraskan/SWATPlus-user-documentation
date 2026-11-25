---
description: Fraction of total impervious area in urban land type
---

# frac\_imp

**Code reference:** `urbdb(iu)%fimp` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/urban_data_module.f90#L7)).

Urban areas differ from rural areas in the fraction of total area that is impervious. Construction of buildings, parking lots and paved roads increases the impervious cover in a watershed and reduces infiltration. With development, the spatial flow pattern of water is altered and the hydraulic efficiency of flow is increased through artificial channels, curbing, and storm drainage and collection systems.

This fraction includes directly and indirectly connected impervious areas.

**Current use:** weights loads from the impervious part against the pervious part in [`hru_urban.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_urban.f90#L153-L172):

$$L = L_{\text{imp}}\,f_{\text{imp}} + L_{\text{perv}}\,(1 - f_{\text{imp}})$$

where $L$ is the total HRU load, $L_{\text{imp}}$ is the impervious-area load, $L_{\text{perv}}$ is the pervious-area load (same load units as $L$), and $f_{\text{imp}}$ is `frac_imp` (dimensionless). It also reduces overland erosion by $(1 - f_{\text{imp}})$ ([`ero_ovrsed.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/ero_ovrsed.f90#L159-L180)), and enters the USGS regression loads ([`regres.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/regres.f90#L77-L79)).
