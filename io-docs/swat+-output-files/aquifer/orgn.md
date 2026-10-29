---
description: "Carbon value under a mismatched nutrient header; see note"
---

# orgn

**Code reference:** `aqu_d(iaq)%cbn` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/aquifer_module.f90#L46)).

This printed header does not identify the quantity correctly: the corresponding value is aquifer carbon, not organic nitrogen. Do not interpret the printed nutrient unit as the unit of this carbon value.

A reliable unit is not assigned here because the printed header and value do not agree.

[Back to the output table](../aquifer.md).
