---
description: Channel water routing method
---

# rte\_cha

**Code reference:** `bsn_cc%rte`

**Declared type:** `basin_control_codes` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/basin_read_cc.f90#L24), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/basin_module.f90#L33)).

There are two channel water routing methods available in SWAT+:

| Code | Option                  |
| ---- | ----------------------- |
| 0    | Variable Storage method |
| 1    | Muskingum method        |

{% hint style="info" %}
The user must be careful to define [msk\_co1](../parameters.bsn/msk_co1.md), [msk\_co2](../parameters.bsn/msk_co2.md) and [msk\_x](../parameters.bsn/msk_x.md) in [**parameters.bsn**](../parameters.bsn/) when the Muskingum method is chosen.
{% endhint %}
