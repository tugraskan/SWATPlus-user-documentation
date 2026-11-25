---
description: >-
  Weighting factor control relative importance of inflow rate and outflow rate
  in determining storage on reach
---

# msk\_x

**Code reference:** `bsn_prm%msk_x` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L106), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L24)).

Muskingum wedge-storage weighting factor ($X$, default `0.2`, range `0–0.3`; values `< 1.e-6` are reset to `0.20` in [`basin_prm_default.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_prm_default.f90#L28)). In [`sd_hydsed_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_hydsed_init.f90#L174-L204), `msk_x` determines the numerical stability step limit $\Delta t_{\max}$ and normalized Muskingum routing weights $C_1, C_2, C_3$:

$$\Delta t_{\max} = 2\,K_m\,(1 - X), \qquad D = 2\,K_m\,(1 - X) + \Delta t$$

where:
- $\Delta t_{\max}$ is the maximum stable routing time step (`hours`),
- $K_m$ is the reach storage time constant (`hours`),
- $X$ is `msk_x` (dimensionless),
- $D$ is the routing denominator (`hours`), and
- $\Delta t$ is the routing time step (`hours`).

$$C_1 = \frac{\max(0,\;\Delta t - 2\,K_m\,X)}{D}, \qquad C_2 = \frac{\Delta t + 2\,K_m\,X}{D}, \qquad C_3 = \frac{2\,K_m\,(1 - X) - \Delta t}{D}$$

where:
- $C_1$, $C_2$, and $C_3$ are the Muskingum routing weights (dimensionless, subsequently normalized so $C_1 + C_2 + C_3 = 1$),
- $K_m$ is the reach storage time constant (`hours`),
- $X$ is `msk_x` (dimensionless),
- $D$ is the routing denominator (`hours`), and
- $\Delta t$ is the routing time step (`hours`).

This parameter is only used when channel routing uses the Muskingum method ([rte\_cha](../codes.bsn/rte_cha.md) = `1`).

{% hint style="info" %}
For reservoir-type storage, there is no wedge and *msk\_x* should be 0.0. For a full wedge, *msk\_x* should be 0.5. For rivers, *msk\_x* will fall between 0.0 and 0.3 with a mean value near 0.2.
{% endhint %}
