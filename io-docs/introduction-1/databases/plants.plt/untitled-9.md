---
description: Exponent that governs LAI decline rate
---

# dlai\_rate

**Code reference:** `pldb(ic)%dlai_rate` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L50)).

Exponent $r$ of the leaf area decline of **annual** plants after [hu\_lai\_decl](untitled-10.md) ([`pl_leaf_senes.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_leaf_senes.f90#L34-L39)):

$$A = A_{0} \left( \frac{1 - h}{1 - d} \right)^{r}$$

where:
- $A$ is the leaf area index (dimensionless),
- $A_{0}$ is the leaf area index when decline began (dimensionless),
- $h$ is the current heat-unit fraction (dimensionless),
- $d$ is the heat-unit fraction when decline began (dimensionless; [hu\_lai\_decl](untitled-10.md)), and
- $r$ is `dlai_rate` (dimensionless; a value of `1` gives a linear decline).
