---
description: "Net change in dissolved salt from aquifer mineral reactions"
---

# dsaq_kg

**Code reference:** `salt_basin(24)` ([calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_balance.f90#L286-L303)).

Net change in dissolved salt from aquifer mineral reactions. The standard aquifer path reads the combined chemistry diagnostic, and the GWFlow path sums its cell mineral diagnostics. The average-annual report leaves this field in cumulative kg.

**Unit:** kg for all reporting periods.

See [reporting periods](basin-salt-balance.md#reporting-periods) for aggregation.

[Back to schema](basin-salt-balance.md).
