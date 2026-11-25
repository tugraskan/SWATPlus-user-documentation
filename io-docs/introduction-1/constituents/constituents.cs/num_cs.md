---
description: "Number of other constituents to simulate"
---

# num\_cs

**Code reference:** `cs_db%num_cs` ([`declaration`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L27), [`read`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constit_db_read.f90#L61-L63)).

Number of other constituents: selenate, selenite and boron. The default is 0, which turns their simulation off. Use 0 or 3.

When it is above 0, the reaction and sorption routines use positions 1 to 3 ([`hru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L252-L256), [`cs_rctn_hru.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_rctn_hru.f90#L57-L60), [`cs_sorb_hru.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_sorb_hru.f90#L73-L75)). A value of 1 or 2 is not rejected, but the routines then reach past the end of the list. This is a suspected model defect.
