---
description: "Organic nitrogen value under a mismatched header; see note"
---

# orgp

**Code reference:** `aqu_d(iaq)%orgn` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/aquifer_module.f90#L47)).

This printed header does not identify the quantity correctly: the corresponding value is the aquifer organic-nitrogen field, not organic phosphorus. Its phosphorus label and printed phosphorus unit are unreliable.

A reliable unit is not assigned here because the printed header and value do not agree.

[Back to the output table](README.md).
