---
description: Fraction of element in Routing Unit
---

# frac

**Code reference:** `ru_elem(i)%frac`

**Declared type:** `routing_unit_elements` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/ru_read_elements.f90#L71), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hydrograph_module.f90#L492)).

The fraction of element in Routing Unit is a weighting factor. Each element’s hydrograph contribution is multiplied by an expansion factor derived from frac. For non-HRU objects, the expansion factor equals frac. For HRUs/HRU-LTEs with frac < 0.99999, the model converts frac into an area expansion factor by multiplying it with the Routing Unit area and then dividing it by the HRU/HRU-LTE area.

{% hint style="danger" %}
The model does not check the frac values. If they do not sum appropriately for a Routing Unit, the routed water/load scaling will reflect that directly.
{% endhint %}
