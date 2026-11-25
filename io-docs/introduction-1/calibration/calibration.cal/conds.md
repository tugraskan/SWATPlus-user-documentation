---
description: Number of conditional filter lines following a calibration.cal record.
---

# conds

**Code reference:** `cal_upd(i)%conds` ([read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parmchg_read.f90#L90-L100), [evaluate](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_conditions.f90#L61-L100)).

Integer count (struct default `0`) of condition lines immediately following the parameter-change record. Two condition-line formats are parsed in [`cal_parmchg_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parmchg_read.f90#L94-L100):

- **Range condition** (`range` `var` `val1` `val2`): used for `res_pvol`, testing whether reservoir principal volume (`m3`) lies within $(10{,}000\,v_1,\, 10{,}000\,v_2)$ in [`cal_conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_conditions.f90#L64).
- **Categorical condition** (`var` `alt` `targ` `targc`): matches `hsg`, `res_typ`, `texture`, `plant`, `pl_class`, `landuse`, or `cal_group` against `targc` in [`cal_conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_conditions.f90#L62-L100) and [`cal_conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_conditions.f90#L184-L225).

*(Note: In SWAT+ main (6f515368), the `alt` and `targ` columns on categorical condition lines are parsed into memory but are not used in simulation calculations).*
