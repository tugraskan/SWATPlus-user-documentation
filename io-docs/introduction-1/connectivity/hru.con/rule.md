---
description: Intended flow-control decision table in flo_con.dtl (does not change outflow in main 6f515368)
---

# rule

**Code reference:** `ob(i)%ruleset` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L351)).

Name of a flow-control decision table in flo\_con.dtl. SWAT+ main (6f515368) [matches the name to a table](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dtbl_flocon_read.f90#L77-L87), but no routing calculation uses the match, so it does not change the outflow of the object. A name that matches no table gives no warning. Use null.
