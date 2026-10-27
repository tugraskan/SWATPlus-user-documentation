---
description: Number of print intervals for average annual output
---

# aa\_int\_cnt

**Code reference:** `pco%aa_numint` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/basin_module.f90#L166)).

If _aa\_int\_cnt_ = 0, the model will print average annual output for the entire period. If _aa\_int\_cnt_ > 0, the end years of the print intervals have to be specified by the user by listing them in chronological order in the same line as _aa\_int\_cnt_.&#x20;

{% hint style="info" %}
Example: If _aa\_int\_cnt_ = 3   1955   1965   1975, average annual results will be printed for the time periods ending in 1955, 1965, and 1975.
{% endhint %}
