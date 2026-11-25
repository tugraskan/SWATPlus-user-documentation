---
description: Fraction of fully channelized flow
---

# cha\_q

**Code reference:** `filtstrip_db(ifiltop)%vfsch` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L35)).

This parameter defines the fraction of the flow within the most concentrated 10% of the filter strip that is fully channelized (range `0.0–0.95`). Flow that is fully channelized bypasses filtering and infiltration effects. In [`smp_filter.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/smp_filter.f90#L90-L91), the concentrated 10% flow is split into filtered ($D_2$) and channelized bypass ($D_3$) drainage areas:

$$D_2 = (1 - f_{\text{ch}}) \, f_{\text{con}} \, A_{\text{hru}}, \qquad D_3 = f_{\text{con}} \, f_{\text{ch}} \, A_{\text{hru}}$$

where $f_{\text{ch}}$ is `cha_q`, $f_{\text{con}}$ is [`con_vfs`](con_vfs.md), and $A_{\text{hru}}$ is HRU area (ha). At runtime ([`structure_set_parms.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/structure_set_parms.f90#L67-L68)), values $\le 0$ are reset to `0.0` and values $> 0.95$ are capped at `0.95`.
