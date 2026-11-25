---
description: "Signed net change in dissolved soil salt from soil chemistry, weighted by HRU area"
---

# dssl_kg

**Code reference:** `salt_basin(23)` ([calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_balance.f90#L279-L284)).

Signed net change in dissolved soil salt from soil chemistry, weighted by HRU area. The first ion slot stores the combined change across the ions. [Soil chemistry](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_chem_hru.f90#L361-L369)

**Unit:** kg for daily, monthly, and yearly output. The average-annual value is kg/yr.

See [reporting periods](basin-salt-balance.md#reporting-periods) for aggregation.

[Back to schema](basin-salt-balance.md).
