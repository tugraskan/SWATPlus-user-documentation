---
description: "Salt in full-HRU soil amendment diagnostics"
---

# amnd_kg

**Code reference:** `salt_basin(17)` ([calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_balance.f90#L209-L217)).

Salt in full-HRU soil amendment diagnostics. The daily basin calculation sets totals below 0.000001 kg to zero.

**Unit:** kg for daily, monthly, and yearly output. The average-annual value is kg/yr.

See [reporting periods](basin-salt-balance.md#reporting-periods) for aggregation.

[Back to schema](basin-salt-balance.md).
