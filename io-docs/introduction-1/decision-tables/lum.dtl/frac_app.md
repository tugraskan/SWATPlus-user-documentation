---
description: Probability of a scheduled application within the window
---

# frac\_app

**Code reference:** `dtbl_lum(i)%frac_app` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditional_module.f90#L50)).

For a `prob_unif` condition row, enter the probability as a fraction between 0 and 1 in the second position, in place of the object type. [`dtbl_lum_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dtbl_lum_read.f90#L69-L75) first reads the ordinary row structure and then rereads its first two fields to store this fraction. The value is table-wide, so a later `prob_unif` row in the same table replaces it.

On the first day of the window, SWAT+ draws a uniform random number and schedules an application when the draw is below this fraction. The single-year branch draws a day in [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L485-L519) as:

$$d = d_0 + 1 + \lfloor U(d_1 - d_0 + 1) \rfloor$$

where $d$ is the selected day of year (day), $d_0$ is the entered first day of the window (day), $d_1$ is the entered last day of the window (day), and $U$ is a uniform random draw in `[0, 1)` (dimensionless). The implemented formula can skip the first day and select the day after the entered end.
