---
description: "Tile drainage released from the HRU"
---

# qtile

**Code reference:** `bwb_d%qtile` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L27)).

Full HRUs report the drainage released from their tile routing store after any saturated-buffer split. GWFlow cell tile delivery is a separate channel calculation. HRU-LTE caps its own tile drainage at 10 mm per day and at the available water. [Calculation and reporting details](README.md#snow-irrigation-and-drainage)

**Unit:** mm.

[Back to the output table](README.md).
