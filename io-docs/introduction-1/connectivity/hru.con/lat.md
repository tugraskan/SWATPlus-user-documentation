---
description: Latitude of the object
---

# lat

**Code reference:** `ob(i)%lat` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L338)).

Latitude of the object in decimal degrees, positive north of the equator (range -90 to 90).

SWAT+ main (6f515368) uses this connect-file value only for HRUs, and only its sign. It sets when the base-zero heat units and the management-schedule skip flag are reset: on [day 181 if the latitude is below 0](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/time_control.f90#L262-L275), otherwise [at the end of the year](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/time_control.f90#L362-L372).
