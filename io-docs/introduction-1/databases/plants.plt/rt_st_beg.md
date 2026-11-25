---
description: >-
  Root fraction of total biomass at the beginning of growth
---

# rt\_st\_beg

**Code reference:** `pldb(ic)%rsr1` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L83)).

Fraction of total biomass in roots at the start of growth. Although the name says root-to-shoot ratio, the model uses it as a root **fraction of total biomass** ([`pl_root_gro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_root_gro.f90#L39-L56)). Values of zero or less are replaced by 0.4 ([`plantparm_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plantparm_init.f90#L26)).

For annuals the fraction moves linearly from this value to [rt\_st\_end](rt_st_end.md) with the heat-unit fraction. For perennials it moves over the first 20% of the years to maturity and then stays at the end value.
