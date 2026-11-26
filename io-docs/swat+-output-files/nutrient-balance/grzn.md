---
description: "Total nitrogen added to soil from grazing"
---

# grzn

**Code reference:** `bnb_d%grazn` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L82)).

On SWAT+ dev both carbon modes record organic plus mineral nitrogen in the grazing manure applied, using the manure_db.frt record named by the grazing operation. The manure goes through the same routine as a `manu` operation, so it is also counted in `fertn`. [diagnostic reset](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/varinit.f90#L96-L100), [grazing manure](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_graze.f90#L89-L96), [manure totals](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_manure.f90#L181-L182).

**Unit:** kg N/ha.

The same printed heading can appear in daily, monthly, yearly, and average-annual variants of this family. The reporting interval changes the row period; this page does not infer a total-versus-average rule beyond what the family output and source establish.

[Back to the output table](README.md).
