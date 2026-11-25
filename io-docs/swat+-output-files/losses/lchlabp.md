---
description: "Soluble (labile) phosphorus leaching past bottom soil layer"
---

# lchlabp

**Code reference:** `bls_d%lchlabp` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L161)).

Daily labile P carried past the bottom soil layer by percolation. The routine initializes the diagnostic to zero, skips the layer indexed by `i_sep(j)`, and writes the bottom-layer amount only when that layer is processed. [leaching assignment](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/nut_solp.f90#L50-L79).

**Unit:** kg P/ha.

The same printed heading can appear in daily, monthly, yearly, and average-annual variants of this family. The reporting interval changes the row period; this page does not infer a total-versus-average rule beyond what the family output and source establish.

[Back to the output table](README.md).
