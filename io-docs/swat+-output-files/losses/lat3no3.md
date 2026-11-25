---
description: "Nitrate nitrogen transported in lateral flow"
---

# lat3no3

**Code reference:** `bls_d%latno3` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L156)).

The printed heading maps to `latno3`. The nitrate routine sums lateral nitrate from the soil layers. At the drain layer, if tile flow is positive, the routine reuses the concentration calculated from the drain layer and lower layers for the lateral and percolation calculations in that layer. The reported lateral value has passed through subsurface storage. The filter-strip buffer and urban concentration-cap branches stay inactive on this revision. See [management settings](README.md#how-management-changes-reported-losses). [nitrate calculation order](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/nut_nlch.f90#L99-L146), [subsurface lag](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/swr_substor.f90#L51-L73), [urban limit](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_urb_bmp.f90#L31-L36).

**Unit:** kg N/ha.

The same printed heading can appear in daily, monthly, yearly, and average-annual variants of this family. The reporting interval changes the row period; this page does not infer a total-versus-average rule beyond what the family output and source establish.

[Back to the output table](README.md).
