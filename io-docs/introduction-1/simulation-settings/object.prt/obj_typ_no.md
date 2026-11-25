---
description: Number of the object to print output for
---

# obj\_typ\_no

**Code reference:** `ob_out(ii)%obtypno` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L262)).

Within-type sequential number of the object to print output for (integer; Fortran struct default: `0`). In [`object_read_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/object_read_output.f90#L58-L75), setting `obj_typ_no = 0` with `obj_typ = hru` sets `ob_out(i)%objno = 0`. In [`obj_output.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/obj_output.f90#L48-L164), `objno = 0` loops over all HRUs in the same file for `sol_water`, `solnut_ly`, `solnut_pr`, and `plant` (and over all SWAT-DEG channels for `cha_fp`). Hydrograph outputs (`tot`, `rhg`, `sur`, `lat`, `til`) require a positive object number.
