---
description: Irrigation code
---

# irr\_flag

**Code reference:** `hlt_db(i)%irr` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_module.f90#L44)).

Intended values are `no_irr` (no irrigation) and `irr` (irrigation).

{% hint style="warning" %}
In SWAT+ main (6f515368), `irr` does not turn irrigation on. The code tests whether the text sorts after `no_irr` ([`hru_lte_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_control.f90#L242)), and `irr` sorts before it. Only a value that sorts after `no_irr` passes the test.
{% endhint %}

When the test passes, irrigation applies only while a crop is growing and the water stress ratio (actual over potential ET) is below 0.8. The depth is the soil water deficit up to 76.2 mm ([`hru_lte_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_control.f90#L241-L265)).
