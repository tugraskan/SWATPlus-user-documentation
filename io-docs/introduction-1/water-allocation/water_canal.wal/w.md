---
description: "Canal bottom width"
---

# w

**Code reference:** `canal(ic)%w` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L198), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_canal_read.f90#L45,L54)).

Canal bottom width (`m`). Enters the canal maximum storage calculation in [`water_canal_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_canal_read.f90#L59):

$$V_{\max} = \frac{(w + s_s \cdot d) \cdot d \cdot L}{1000}$$

where $w$ is bottom width (`m`), $s_s$ is side slope (`m/m`), $d$ is depth (`m`), $L$ is length (`km`), and $V_{\max}$ is `canal(ic)%stor_mx` (used by the `fill_can` decision-table action in [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L236)). Note that with $L$ in `km`, dividing by `1000` yields `10^-6 * m^3` rather than `m^3`. Also copied into `gwflow` canal seepage tables in [`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1260,L1267).
