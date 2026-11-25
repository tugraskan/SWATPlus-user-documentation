---
description: "Organic-nitrogen component under a mismatched phosphorus heading"
---

# orgp

**Code reference:** `aqu_d(iaq)%orgn` ([declaration and default](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aquifer_module.f90#L47)).

The printed `orgp` position contains the component named `orgn`, not organic phosphorus. Its declaration calls it organic nitrogen but annotates its unit as `kg/ha P`; the printed heading and units also imply phosphorus. These annotations conflict.

**Unit:** unresolved source unit. No direct update to this component was identified in the inspected 1-D controller; its declared default is zero. This is not evidence of an active organic-phosphorus calculation.

The addition operator sums this component and the multiply operator applies basin area weights. Monthly and yearly rows sum its daily values, rather than average a stored nutrient mass; the average-annual operator divides by reporting years ([operators](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aquifer_module.f90#L175)).

[Back to the output table](README.md).
