---
description: Multiplier for the variable-storage channel-routing coefficient
---

# scoef

**Code reference:** `bsn_prm%scoef` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L110), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L24)).

Dimensionless multiplier (default `1`, range `0–1`) applied to the Variable Storage routing coefficient when [rte\_cha](../codes.bsn/rte_cha.md) = `0` in [`ch_rtmusk.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_rtmusk.f90#L153-L155):

$$\text{SC} = \min\!\left(1,\; \text{scoef} \cdot \frac{2\,\Delta t}{2\,T_{\text{out}} + \Delta t}\right), \qquad Q_{\text{out}} = \text{SC} \cdot V_{\text{stor}}$$

where $\Delta t$ is the routing timestep (`hours`), $T_{\text{out}}$ is reach travel time (`hours`), and $V_{\text{stor}}$ is total reach storage (`m^3`).
