---
description: Lag parameter for smoothing reservoir outflow when outflow is decreasing or unchanged
---

# shp\_co2

**Code reference:** `res_hyddb(ires)%br2` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L77)).

Dimensionless lag parameter for smoothing reservoir outflow when outflow decreases or remains unchanged (`0.0` default; disables smoothing). During initialization ([`res_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_initial.f90#L59)), SWAT+ copies `shp_co2` to `res_ob%lag_down`. It is not used as an area–volume shape coefficient; SWAT+ derives those parameters from [area\_ps](area_ps.md), [vol\_ps](vol_ps.md), [area\_es](area_es.md), and [vol\_es](vol_es-1.md).

When the newly calculated release is less than or equal to the previous day's outflow ($Q_{\text{prev}} \ge Q_{\text{new}}$), [`res_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_control.f90#L148-L157) smooths the outflow as:

$$\alpha_{\text{down}} = \exp(-\text{shp}_{2}), \qquad Q_{\text{out}} = \alpha_{\text{down}} Q_{\text{new}} + (1 - \alpha_{\text{down}}) Q_{\text{prev}}$$

where $\text{shp}_{2}$ is `shp_co2`, $Q_{\text{new}}$ is the unsmoothed daily outflow ($\text{m}^3$), $Q_{\text{prev}}$ is the previous day's outflow ($\text{m}^3$), and $Q_{\text{out}}$ is the lagged outflow ($\text{m}^3$).
