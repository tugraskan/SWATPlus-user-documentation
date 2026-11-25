---
description: "Flow rate in each listed channel"
---

# flow rate (m3/sec)

**Code reference:** `ch_out_d(chan_id)%flo` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_str_output.f90#L29)).

**Printed header value:** `first set of columns:   flow rate (m3/sec)` ([header](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_cha_read.f90#L77)).

The first set of columns holds the streamflow of each channel listed in `cs_streamobs`, in the order of that list. The source comment gives the unit as m3/sec. The values are written with an `e14.6` edit descriptor. [Value loop](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_str_output.f90#L25-L30), [format](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_str_output.f90#L68)

**Type:** real. **Unit:** m3/sec.

[Back to the output table](../channel-stream-observation.md).
