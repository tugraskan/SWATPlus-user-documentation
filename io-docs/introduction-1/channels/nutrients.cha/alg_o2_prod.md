---
description: Oxygen production rate per unit of algal photosynthesis
---

# alg\_o2\_prod

**Code reference:** `ch_nut(ich)%ai3` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/channel_data_module.f90#L141)).

Mass of oxygen produced per unit mass of algal photosynthesis (`mg O2/mg alg`, default `1.60`, range `1.40–1.80`). In [`ch_read_nut.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_nut.f90#L67), values `<= 0.` are replaced with `1.60`.

In [`ch_watqual4.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_watqual4.f90#L272), `ai3` enters the algal oxygen mass-rate term:

$$M_{\text{alg,O2}} = \alpha_4\,M_{\text{alg,2}} + \alpha_3\,M_{\text{alg,1}}$$

where:
- $M_{\text{alg,O2}}$ is the algal dissolved-oxygen mass-rate term (`alg_m_o2`),
- $\alpha_4$ is `alg_o2_resp` (`mg O2/mg alg`),
- $M_{\text{alg,2}}$ is the algal respiration biomass term (`alg_m2`),
- $\alpha_3$ is `alg_o2_prod` (`mg O2/mg alg`), and
- $M_{\text{alg,1}}$ is the algal growth biomass term (`alg_m1`).

However, from source reading at `6f515368`, [`ch_watqual4.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_watqual4.f90#L278-L280) omits `alg_m_o2` from the dissolved oxygen source/sink term `factm`, so `alg_o2_prod` does not affect simulated dissolved oxygen.
