---
description: "Nitrate nitrogen stored in the aquifer"
---

# no3_st

**Code reference:** `aqu_d(iaq)%no3_st` ([1-D calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L138)).

Stored nitrate-nitrogen amount, rather than water concentration. The daily controller adds incoming nitrate divided by aquifer area and subtracts discharge, first-order loss, and seepage. However, initialization multiplies a water volume by concentration to produce kg, without dividing by area, before daily calculations treat this component as kg N/ha. Canal additions also use hydrograph nitrate mass directly. These are source mass-basis inconsistencies; the declared unit is not proof of correct accounting in every configuration.

**Unit:** kg N/ha in the daily convention; see source inconsistencies.

The `no3_init` calibration branch also converts the concentration to whole-aquifer kg. The allocation withdrawal path reports a nitrate load from storage after reducing it, using the same fraction that reduced the original storage. [Nitrate calibration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L940-L945), [aquifer withdrawal](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_withdraw.f90#L115-L123).

Monthly output divides the sum of daily values by the calendar month's day count. Yearly output sums those monthly means and divides by 12, so it gives equal weight to months rather than to days. Average-annual output divides the accumulated yearly means by `time%yrs_prt`. These fixed month/year divisors are also used at partial reporting boundaries. A final partial month is omitted from the yearly and average-annual state calculations.

Basin output applies `aqu_prm(iaq)%area_ha / bsn%area_tot_ha`; the denominator is the full basin area, not the sum of aquifer areas. This is not necessarily a normalized mean over just the aquifers.

Source: [initial nitrate mass](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_initial.f90#L175) and [canal additions](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_canal.f90#L43).

[Back to the output table](README.md).
