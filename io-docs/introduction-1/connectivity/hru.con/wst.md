---
description: Weather station name
---

# wst

**Code reference:** `ob(i)%wst_c` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L347)).

The wst value is a foreign key matching the name field in weather-sta.cli. SWAT+ uses that name to resolve the weather-station record for the object.

A name that matches no station, including `null`, [leaves the object on the first station](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L348) in weather-sta.cli with no warning.

{% hint style="warning" %}
SWAT+ looks the name up with a [binary search](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/search.f90#L18-L44) and [does not sort the station names](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_staread.f90#L64-L70). Keep weather-sta.cli sorted by name; otherwise a valid name can be missed.
{% endhint %}
