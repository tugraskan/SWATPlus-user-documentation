---
description: "Date as year × 1000 + day of year"
---

# value

**Code reference:** `combined_yrday` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L189), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L610-L612)).

Date of a `head_output_time` record, written as year × 1000 + day of year (for example 2010152). SWAT+ splits it into year and day ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L610-L612)). When the simulation reaches the first listed date it moves on to the next one, but writes nothing ([`gwflow_simulate.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_simulate.f90#L388-L393)). *(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
