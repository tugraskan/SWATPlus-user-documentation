---
description: Ending day of the simulation
---

# day\_end

**Code reference:** `time%day_end` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_module.f90#L31)).

SWAT+ is able to end a simulation at any day of the year. This option can for example be useful, if the user wishes to simulate hydrological years instead of calendar years.

Read in [`time_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_read.f90#L28), `day_end` applies only to the final simulation year (`time%yrs == time%nbyr`) in [`time_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_control.f90#L139-L143): if `day_end <= 0`, the final year runs through December 31 (`365`, or `366` in a leap year); if `day_end > 0`, it is clamped to `min(day_end, ndays(13))` so entering `366` in a non-leap year ends on day `365`.

{% hint style="info" %}
If _day\_end_ = 0, the model will end the simulation on December 31st.

If the simulation ends after the last day of the observed climate data, SWAT+ will use simulated climate data for the time period after the end of the observed climate data.
{% endhint %}
