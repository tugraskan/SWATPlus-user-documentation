---
description: "Water stored in the aquifer"
---

# stor

**Code reference:** `aqu_d(iaq)%stor` ([1-D calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L97)).

Water storage as an equivalent depth over aquifer area. The 1-D controller adds recharge and subtracts groundwater flow, seepage, and revap. Water-table depth is calculated earlier in that sequence. Canal seepage can also add hydrograph water volume directly without the usual conversion to mm; the source does not establish a consistent water-depth basis for every allocation configuration.

**Unit:** mm.

In the initializer, the aquifer's storage formula reads water-table depth using the parameter-record index in the object array. The two indices can differ. Allocation withdrawal can also report less water delivered than it removes from storage, because it calculates delivery from the remaining storage. [Initialization and allocation details](README.md#initialization-and-water-allocation).

Monthly output divides the sum of daily values by the calendar month's day count. Yearly output sums those monthly means and divides by 12, so it gives equal weight to months rather than to days. Average-annual output divides the accumulated yearly means by `time%yrs_prt`. These fixed month/year divisors are also used at partial reporting boundaries. A final partial month is omitted from the yearly and average-annual state calculations.

Basin output applies `aqu_prm(iaq)%area_ha / bsn%area_tot_ha`; the denominator is the full basin area, not the sum of aquifer areas. This is not necessarily a normalized mean over just the aquifers.

[Back to the output table](README.md).
