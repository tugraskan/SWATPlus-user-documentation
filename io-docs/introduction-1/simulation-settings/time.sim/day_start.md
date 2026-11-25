---
description: Beginning day of the simulation
---

# day\_start

**Code reference:** `time%day_start` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_module.f90#L29)).

SWAT+ is able to begin a simulation at any day of the year. This option can for example be useful, if the user wishes to simulate hydrological years instead of calendar years.

If `day_start <= 0`, [`time_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_read.f90#L31) resets `time%day_start` to `1` (January 1). For all subsequent simulation years after the first year (`time%yrs > 1`), [`time_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_control.f90#L134-L136) resets `time%day_start = 1` so each later year starts on January 1.

{% hint style="info" %}
If _day\_start_ = 0, the model will start the simulation on January 1st.

If the simulation begins before the first day of the observed climate data, SWAT+ will use simulated climate data for the time period before the start of the observed climate data.
{% endhint %}
