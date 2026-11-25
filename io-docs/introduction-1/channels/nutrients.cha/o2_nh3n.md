---
description: Oxygen uptake rate per unit of NH3-N oxidation
---

# o2\_nh3n

**Code reference:** `ch_nut(ich)%ai5` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/channel_data_module.f90#L143)).

Mass of dissolved oxygen consumed per unit mass of ammonia nitrogen oxidized to nitrite (`mg O2/mg N`, default `3.50`, range `3.00–4.00`). In [`ch_read_nut.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_nut.f90#L69), values `<= 0.` are replaced with `3.5`.

In [`ch_watqual4.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_watqual4.f90#L276-L279), `ai5` multiplies the ammonia-oxidation mass-rate term `bc1_m` in the dissolved oxygen source/sink expression `factm`:

$$\text{factm}_{\text{O2}} = \text{rk1}_m + \text{rk2}_m - \text{rs4}_k + \text{bc1}_m \alpha_5 + \text{bc2}_m \alpha_6$$

where:
- $\text{factm}_{\text{O2}}$ is the dissolved oxygen source/sink mass-rate term (`factm`),
- $\text{rk1}_{m}$ is the CBOD deoxygenation mass-rate term (`rk1_m`),
- $\text{rk2}_{m}$ is the reaeration mass-rate term (`rk2_m`),
- $\text{rs4}_{k}$ is the benthic oxygen demand term (`rs4_k`),
- $\text{bc1}_{m}$ is the ammonia-oxidation mass-rate term (`bc1_m`),
- $\alpha_5$ is `o2_nh3n` (`mg O2/mg N`),
- $\text{bc2}_{m}$ is the nitrite-oxidation mass-rate term (`bc2_m`), and
- $\alpha_6$ is `o2_no2n` (`mg O2/mg N`).
