---
description: "Accumulated base-zero heat-unit fraction"
---

# phubas0

**Code reference:** `hpw_d(j)%phubase0 = phubase(j)` ([assignment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L869)).

Accumulated base-zero heat-unit fraction. When mean air temperature is positive and the weather generator's total heat units exceed 0.01, the calculation adds `w%tave / wgn_pms(iwgn)%phutot` ([calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L229)). HRU-LTE uses the station accumulator, which resets before output on the day marked as year end. Full HRUs use a separate accumulator with hemisphere-specific reset dates. Longer-period plant/weather rows average the fraction over reporting days. [Daily heat-unit calculations](plant-weather-output.md#daily-weather-and-heat-units)

**Unit:** frac (dimensionless). The printed units row says `degc`, while the declaration says `deg c/deg c`; the normalized calculation establishes the fraction interpretation.

[Back to the plant and weather schema](plant-weather-output.md).
