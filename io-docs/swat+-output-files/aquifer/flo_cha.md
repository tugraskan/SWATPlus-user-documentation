---
description: "Groundwater flow assigned to channel receivers"
---

# flo_cha

**Code reference:** `aqu_d(iaq)%flo_cha` ([routing calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L380)).

Groundwater flow assigned to channel receivers. The controller sums `aqu_d(iaq)%flo * frac_out` only for outgoing connections whose hydrograph type is `tot` and whose receiver type is `cha` or `sdc`.

**Unit:** mm.

Monthly values sum daily exchanges; yearly values sum the monthly totals. Average-annual values divide the accumulated yearly totals by `time%yrs_prt`.

Basin output applies `aqu_prm(iaq)%area_ha / bsn%area_tot_ha`; the denominator is the full basin area, not the sum of aquifer areas. This is not necessarily a normalized mean over just the aquifers.

[Back to the output table](README.md).
