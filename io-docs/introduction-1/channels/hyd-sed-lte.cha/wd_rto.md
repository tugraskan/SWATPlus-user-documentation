---
description: Channel sinuosity
---

# sinu

**Code reference:** `sd_chd(idb)%sinu`

**Declared type:** `swatdeg_hydsed_data` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/sd_hydsed_read.f90#L61), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/sd_channel_module.f90#L29)).

Channel sinuosity is a measure of how much a river or stream channel deviates from a straight line between two points. It is calculated by dividing the length of the channel by the straight-line distance between its endpoints.&#x20;

For rivers, the conventional classes of sinuosity are:

| Sinuosity       | Channel Form    |
| --------------- | --------------- |
| < 1.05          | almost straight |
| ≥ 1.05 - < 1.25 | winding         |
| ≥ 1.25 - < 1.50 | twisty          |
| ≥ 1.50          | meandering      |
