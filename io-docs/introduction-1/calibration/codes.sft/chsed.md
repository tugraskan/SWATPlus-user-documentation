---
description: Channel sediment soft-calibration switch.
---

# chsed

**Code reference:** `cal_codes%chsed` ([read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_read_codes.f90#L34), [output](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_control.f90#L108-L159)).

Intended switch (`"y"` or `"n"`, struct default `"n"`) for channel-sediment soft calibration. In SWAT+ main (`6f515368`), setting `"y"` accumulates channel widening, downcutting, and headcut averages in [`calsoft_sum_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_sum_output.f90#L152) and [`calsoft_ave_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_ave_output.f90#L97) (only when `sed`, `plt`, `hyd_hru`, and `hyd_hrulte` are all `"n"`) and writes `hru-new.cal` entries at [`calsoft_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_control.f90#L159), but no routine updates `chcal%ord%prm%erod`.
