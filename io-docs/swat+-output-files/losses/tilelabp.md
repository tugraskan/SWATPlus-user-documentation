---
description: "Soluble (labile) phosphorus in tile flow"
---

# tilelabp

**Code reference:** `bls_d%tilelabp` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L162)).

Daily labile P removed from the drain layer by tile flow. The routine calculates it after percolation has removed some labile P from that layer. The diagnostic stays zero when the drain layer is the layer indexed by `i_sep(j)`. [tile P assignment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/nut_solp.f90#L59-L100).

**Unit:** kg P/ha.

The HRU routing routine adds this tile phosphorus mass to the soluble P of the surface hydrograph. [hydrograph P assignment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_hyds.f90#L62-L74).

The same printed heading can appear in daily, monthly, yearly, and average-annual variants of this family. The reporting interval changes the row period; this page does not infer a total-versus-average rule beyond what the family output and source establish.

[Back to the output table](README.md).
