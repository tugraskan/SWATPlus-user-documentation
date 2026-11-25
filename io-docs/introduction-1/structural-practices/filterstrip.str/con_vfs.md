---
description: Fraction of flow entering the most concentrated 10% of the filter strip
---

# con\_vfs

**Code reference:** `filtstrip_db(ifiltop)%vfscon` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L34)).

Runoff generated upslope of a filter strip is not uniformly distributed across the entire length of the strip; 10% of the filter strip typically receives between 25% and 75% of the runoff from the field (range `0.25–0.75`). In [`smp_filter.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/smp_filter.f90#L89-L91), SWAT+ partitions the upslope drainage area among the outer 90% section ($D_1$), the non-channelized concentrated 10% section ($D_2$), and the fully channelized bypass ($D_3$) as:

$$D_1 = (1 - f_{\text{con}}) \, A_{\text{hru}}, \qquad D_2 = (1 - f_{\text{ch}}) \, f_{\text{con}} \, A_{\text{hru}}, \qquad D_3 = f_{\text{con}} \, f_{\text{ch}} \, A_{\text{hru}}$$

where $f_{\text{con}}$ is `con_vfs`, $f_{\text{ch}}$ is [`cha_q`](cha_q.md), and $A_{\text{hru}}$ is HRU area (ha). At runtime ([`structure_set_parms.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/structure_set_parms.f90#L63-L65)), values $\le 0$ are set to `0.5`, positive values $\le 0.1$ are clamped to `0.1`, and values $> 0.95$ are capped at `0.95`.
