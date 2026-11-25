---
description: Percolation coefficient
---

# perco

**Code reference:** `hyd_db(ithyd)%perco` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hydrology_data_module.f90#L21)).

Dimensionless input $p$ that controls the multiplier for seepage from the bottom soil layer. For HRUs with a tile drain, [`topohyd_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/topohyd_init.f90#L54-L66) sets $p$ to `0.1` before converting it. For $p > 10^{-9}$, the initialization uses:

$$F = \min\left(1, \; \exp\left[-1.0052 \ln\left(-\ln(p - 10^{-6})\right) - 5.6862\right]\right)$$

where $F$ is the bottom-layer seepage multiplier (dimensionless) and $p$ is `perco` (dimensionless).

For smaller inputs it sets $F$ to `0`. The nested logarithms have a domain problem when $10^{-9} < p \leq 10^{-6}$, flagged as a suspected model issue. [`swr_percmicro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/swr_percmicro.f90#L104-L107) multiplies bottom-layer seepage by $F$.
