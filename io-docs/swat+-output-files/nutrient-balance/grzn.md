---
description: "Total nitrogen added to soil from grazing"
---

# grzn

**Code reference:** `bnb_d%grazn` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L82)).

The static carbon routine (`cswat = 0`) records organic plus mineral nitrogen in applied grazing manure. The SWAT-C branch (`cswat = 2`) applies manure to soil pools and leaves the diagnostic at its daily reset value. [diagnostic reset](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/varinit.f90#L96-L100), [grazing branches](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/pl_graze.f90#L83-L110).

**Unit:** kg N/ha.

The same printed heading can appear in daily, monthly, yearly, and average-annual variants of this family. The reporting interval changes the row period; this page does not infer a total-versus-average rule beyond what the family output and source establish.

[Back to the output table](README.md).
