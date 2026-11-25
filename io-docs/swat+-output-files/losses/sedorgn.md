---
description: "Sediment-associated organic nitrogen"
---

# sedorgn

**Code reference:** `bls_d%sedorgn` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L153)).

Sediment-associated organic nitrogen after the HRU's routing and adjustments. The lateral sediment routine can add organic N, and wetland outflow can contribute. The particulate-P cap in the urban BMP code targets this slot, but the concentration-cap inputs that would activate that branch stay zero on this revision. See [management settings](README.md#how-management-changes-reported-losses). [lateral contribution](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/swr_latsed.f90#L48-L53), [wetland contribution](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wetland_control.f90#L260-L268), [urban BMP assignment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_urb_bmp.f90#L42-L50).

**Unit:** kg N/ha.

The same printed heading can appear in daily, monthly, yearly, and average-annual variants of this family. The reporting interval changes the row period; this page does not infer a total-versus-average rule beyond what the family output and source establish.

[Back to the output table](README.md).
