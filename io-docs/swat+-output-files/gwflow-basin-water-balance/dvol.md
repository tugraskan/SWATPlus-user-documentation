---
description: "Change in groundwater storage during the reporting period"
---

# dvol

**Code reference:** `gw_hyd_grid_mo%chng` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L118)).

The net change in groundwater storage during the reporting period. It is accumulated from the daily after-storage minus before-storage values; it is not the total volume stored at the end of the period.

**Unit:** mm.

Monthly and yearly values sum the daily `vaft_grid - vbef_grid` differences. Average-annual output divides their simulation sum by `real(time%nbyr)`, the configured simulation-year count, rather than `time%yrs_prt`.

`vbef` is calculated at the start of the lateral-solution section, after some exchange routines can already have changed heads. The difference therefore follows those source checkpoints; it is not proof of a complete start-of-day to end-of-day storage change. See [vbef](vbef.md) and the [daily accumulation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L900).

[Back to the longer-period basin water-balance schema](longer-period-basin-water-balance.md).
