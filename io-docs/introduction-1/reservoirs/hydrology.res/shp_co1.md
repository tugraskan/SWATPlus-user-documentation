---
description: Lag parameter for smoothing reservoir outflow when outflow is increasing
---

# shp\_co1

**Code reference:** `res_hyddb(ires)%br1` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L76)).

Dimensionless lag parameter for smoothing reservoir outflow when outflow increases (`0.0` default; disables smoothing). During initialization ([`res_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_initial.f90#L58)), SWAT+ copies `shp_co1` to `res_ob%lag_up`. It is not used as an area–volume shape coefficient; SWAT+ derives those parameters from [area\_ps](area_ps.md), [vol\_ps](vol_ps.md), [area\_es](area_es.md), and [vol\_es](vol_es-1.md).

When the newly calculated release exceeds the previous day's outflow ($Q_{\text{prev}} < Q_{\text{new}}$), [`res_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_control.f90#L147-L155) smooths the outflow as:

$$\alpha_{\text{up}} = \exp(-\text{shp}_{1}), \qquad Q_{\text{out}} = \alpha_{\text{up}} Q_{\text{new}} + (1 - \alpha_{\text{up}}) Q_{\text{prev}}$$

where $\text{shp}_{1}$ is `shp_co1`, $Q_{\text{new}}$ is the unsmoothed daily outflow ($\text{m}^3$), $Q_{\text{prev}}$ is the previous day's outflow ($\text{m}^3$), and $Q_{\text{out}}$ is the lagged outflow ($\text{m}^3$).
