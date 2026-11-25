---
description: "Flow storage in the channel"
---

# flo_stor

**Code reference:** `ch_stor(ichan)%flo` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L32)).

Current in-channel water volume after routing, transmission loss, and evaporation. The router tracks overbank floodplain storage in a separate state, which is excluded from this column. [Storage partition](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_rtmusk.f90#L175-L186) · [Channel losses](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_rtmusk.f90#L192-L227)

**Unit:** m3.

The same printed heading can appear in daily, monthly, yearly, and average-annual variants of this family. The reporting interval changes the row period; this page does not infer a total-versus-average rule beyond what the family output and source establish.

[Back to the SD channel general schema](sd-channel-general.md).
