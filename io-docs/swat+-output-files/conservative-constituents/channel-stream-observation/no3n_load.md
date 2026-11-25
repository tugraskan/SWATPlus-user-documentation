---
description: "Nitrate load in each listed channel"
---

# no3n load (kg/day)

**Code reference:** `ch_out_d(chan_id)%no3` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_str_output.f90#L59)).

**Printed header value:** `sixth set of columns:   no3n load (kg/day)` ([header](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_cha_read.f90#L82)).

The sixth set of columns holds the `no3` value of the channel output record for each listed channel. The source comment labels it the no3 load and gives the unit as kg/day. The values are written with an `e14.6` edit descriptor. [Value loop](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_str_output.f90#L55-L60), [format](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_str_output.f90#L68)

**Type:** real. **Unit:** kg/day.

[Back to the output table](../channel-stream-observation.md).
