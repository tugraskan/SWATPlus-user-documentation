---
description: >-
  Root fraction of total biomass at the end of growth
---

# rt\_st\_end

**Code reference:** `pldb(ic)%rsr2` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L84)).

Root fraction of total biomass at the end of growth (see [rt\_st\_beg](rt_st_beg.md); [`pl_root_gro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_root_gro.f90#L39-L56)). Values of zero or less are replaced by 0.2, and tuber plant types are always set to 0.7 ([`plantparm_init.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/plantparm_init.f90#L28-L36)).
