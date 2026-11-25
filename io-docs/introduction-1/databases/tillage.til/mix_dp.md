---
description: Depth of mixing caused by the tillage operation
---

# mix\_dp

**Code reference:** `tilldb(itl)%deptil` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/tillage_data_module.f90#L22)).

Depth of mixing, in mm. A value of 0 mixes nothing; a positive value below 10 is raised to 11 mm ([`mgt_newtillmix_cswat0.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_newtillmix_cswat0.f90#L123-L131)). The layer that contains the depth is mixed in proportion to the part above it ([`mgt_newtillmix_cswat0.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_newtillmix_cswat0.f90#L133-L147)).
