---
description: "Depth from the ground surface to the water table"
---

# dep_wt

**Code reference:** `aqu_d(iaq)%dep_wt` ([1-D calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L105)).

The depth is calculated as `dep_bot - stor / (1000 * spyld)` and bounded below by zero. This calculation follows recharge and any point-of-diversion allocation but precedes subtraction of groundwater flow, seepage, and revap. It is not recalculated after those subtractions, so it need not match the subsequently reported storage at the same daily update point.

**Unit:** m.

Monthly output divides the sum of daily values by the calendar month's day count. Yearly output sums those monthly means and divides by 12, so it gives equal weight to months rather than to days. Average-annual output divides the accumulated yearly means by `time%yrs_prt`. These fixed month/year divisors are also used at partial reporting boundaries. A final partial month is omitted from the yearly and average-annual state calculations.

Basin output applies `aqu_prm(iaq)%area_ha / bsn%area_tot_ha`; the denominator is the full basin area, not the sum of aquifer areas. This is not necessarily a normalized mean over just the aquifers.

[Back to the output table](README.md).
