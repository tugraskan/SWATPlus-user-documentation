---
description: Channel water routing method
---

# rte\_cha

**Code reference:** `bsn_cc%rte` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L33), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_cc.f90#L24)).

Selects the channel water routing method in [`ch_rtmusk.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_rtmusk.f90#L139-L156) and sub-step initialization in [`sd_hydsed_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_hydsed_init.f90#L182-L184) (struct default `0`).

| Code | Option |
| ---- | ------ |
| 0 | Variable Storage method |
| 1 | Muskingum method |

{% hint style="info" %}
When `rte_cha = 0`, storage routing uses [scoef](../parameters.bsn/scoef.md). When `rte_cha = 1`, define [msk\_co1](../parameters.bsn/msk_co1.md), [msk\_co2](../parameters.bsn/msk_co2.md), and [msk\_x](../parameters.bsn/msk_x.md) in [**parameters.bsn**](../parameters.bsn/).
{% endhint %}
