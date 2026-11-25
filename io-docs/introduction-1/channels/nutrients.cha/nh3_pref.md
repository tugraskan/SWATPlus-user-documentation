---
description: Algal preference factor for ammonia
---

# nh3\_pref

**Code reference:** `ch_nut(ich)%p_n` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/channel_data_module.f90#L155)).

Dimensionless algal preference factor for ammonia relative to nitrate (default `0.50`, range `0.0–1.0`). In [`ch_read_nut.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_nut.f90#L80), values `<= 0.` are replaced with `0.5`.

In [`ch_watqual4.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_watqual4.f90#L218-L221), `p_n` computes the ammonia uptake fraction for `alg_no3_m` and `alg_nh4_m`:

$$f_1 = \frac{p_n C_{\text{nh3}}}{p_n C_{\text{nh3}} + (1 - p_n) C_{\text{no3}} + 10^{-6}}$$

where $f_1$ is the ammonia uptake fraction (dimensionless), $p_n$ is `nh3_pref` (dimensionless), $C_{\text{nh3}}$ is reach ammonia concentration (`mg N/L`), and $C_{\text{no3}}$ is reach nitrate concentration (`mg N/L`).

However, from source reading at `6f515368`, [`ch_watqual4.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_watqual4.f90#L284-L301) does not apply `alg_nh4_m` or `alg_no3_m` to reach `nh3` or `no3` updates, so `nh3_pref` does not alter simulated nitrogen concentrations.
