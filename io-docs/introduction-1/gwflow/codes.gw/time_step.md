---
description: "Flow time step in days"
---

# time_step

**Code reference:** `gw_time_step` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L8), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L253)).

Length of the groundwater flow time step, in days. Each day is divided into whole flow steps ([`gwflow_simulate.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_simulate.f90#L340), [`gwflow_lateral.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_lateral.f90#L32-L41)):

$$n = \operatorname{int}(1 / \Delta t)$$

where $n$ is the number of flow steps per day and $\Delta t$ is `time_step` (days).

Choose $\Delta t$ so that $1/\Delta t$ is a whole number (1, 0.5, 0.25, …). Otherwise the fraction is dropped and the steps no longer cover a full day: 0.3 gives three steps, 0.9 days. A value above 1 gives no steps, so no lateral flow is computed. SWAT+ does not check the value.
