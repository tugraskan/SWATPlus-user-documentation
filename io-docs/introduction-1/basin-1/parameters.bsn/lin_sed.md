---
description: Pesticide groundwater mixing-volume factor
---

# lin\_sed

**Code reference:** `bsn_prm%pestgwfact` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L85), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L24)).

Despite the legacy `lin_sed` column label, SWAT+ main (`6f515368`) reads this field into `pestgwfact` (default `0`, range `0–1`, dimensionless) and uses it as the aquifer storage mixing-volume factor for pesticide concentration calculations in [`aqu_1d_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L340-L342):

$$V_{\text{mix}} = S_{\text{aqu}}\,f_{\text{gw}} + Q_{\text{flo}} + Q_{\text{revap}} + Q_{\text{seep}}, \qquad C_{\text{pest}} = \frac{M_{\text{pest}}}{V_{\text{mix}}}$$

where $V_{\text{mix}}$ is the effective mixing volume (`mm`), $S_{\text{aqu}}$ is aquifer storage (`mm`), $f_{\text{gw}}$ is `lin_sed`, $Q_{\text{flo}}$, $Q_{\text{revap}}$, and $Q_{\text{seep}}$ are aquifer return flow, revap, and seepage (`mm`), and $M_{\text{pest}}$ is dissolved aquifer pesticide mass.
