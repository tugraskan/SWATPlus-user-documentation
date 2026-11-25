---
description: "Surface-runoff run-on from upland landscape"
---

# surq_runon

**Code reference:** `bwb_d%surq_runon` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L29)).

Full HRUs add the incoming surface volume directly to the tile contribution converted to depth over the receiving HRU. The printed value therefore mixes m³ and mm where both terms contribute. The wetland inflow branch bypasses this diagnostic. HRU-LTE reports zero. [Calculation and reporting details](README.md#run-on-and-water-yield)

**Unit:** Printed as mm. The source combines m³ and mm.

[Back to the output table](README.md).
