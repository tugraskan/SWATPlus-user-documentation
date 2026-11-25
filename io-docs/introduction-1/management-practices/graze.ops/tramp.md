---
description: Intended daily dry biomass removal by trampling (fraction reset to zero)
---

# bm\_tramp

**Code reference:** `grazeop_db(igrazop)%tramp` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L127), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_grazeops.f90#L49)).

Intended daily dry biomass removal by trampling (`(kg/ha)/day`; default `0.0`, valid range `0.0–500.0`). In SWAT+ main (`6f515368`), [`pl_graze.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_graze.f90#L59-L60) computes a trampled biomass fraction:

$$f_{\text{tramp}} = \frac{B_{\text{tramp}}}{B_{\text{abg}}}$$

where $f_{\text{tramp}}$ is the trampled fraction of community above-ground biomass (dimensionless), $B_{\text{tramp}}$ is `bm_tramp` (`(kg/ha)/day`), and $B_{\text{abg}}$ is total community above-ground biomass (`pl_mass(j)%ab_gr_com%m`, `kg/ha`). However, line `60` immediately overwrites `tramp_plant` with `0.0`, leaving no active simulation effect.

For the intended trampling process, trampling becomes more significant as the number of grazing animals per hectare increases. The input has conventionally been set equal to [bm\_eat](eat.md), assuming that animals trample as much as they eat. This guidance describes intended behavior, not a current calibration effect.
