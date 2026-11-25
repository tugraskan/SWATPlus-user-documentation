---
description: "Canal depth"
---

# d

**Code reference:** `canal(ic)%d` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L199), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_canal_read.f90#L45,L54)).

Canal depth (`m`). Enters the canal maximum storage calculation in [`water_canal_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_canal_read.f90#L59):

$$V_{\max} = \frac{(w + s_s \cdot d) \cdot d \cdot L}{1000}$$

where:

- $V_{\max}$ is `canal(ic)%stor_mx` (used by the `fill_can` decision-table action in [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L236); with $L$ in `km`, dividing by `1000` yields `10^-6 * m^3` rather than `m^3`)
- $w$ is bottom width (`m`)
- $s_s$ is side slope (`m/m`)
- $d$ is `d` (`m`)
- $L$ is length (`km`)

It also enters daily canal seepage in [`wallo_canal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_canal.f90#L35) and is copied into `gwflow` canal structures in [`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1261,L1268):

$$V_{\text{seep}} = K_{\text{sat}} \cdot d \cdot L$$

where $V_{\text{seep}}$ is daily canal seepage ($\text{m}^3\text{/d}$), $K_{\text{sat}}$ is [sat_con](sat_con.md) (`mm/day`), $d$ is `d` (`m`), and $L$ is length (`km`).
