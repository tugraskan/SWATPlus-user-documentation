---
description: "Salt in Recall's within-watershed point-source diagnostic"
---

# ptso_kg

**Code reference:** `salt_basin(19)` ([calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_balance.f90#L229-L236)).

Salt in Recall's within-watershed point-source diagnostic. For file-based salt series, the reader classifies a title token of Incoming as outside the watershed and other title tokens as within it. [Source classification](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_salt.f90#L121-L127)

**Unit:** kg for daily, monthly, and yearly output. The average-annual value is kg/yr.

See [reporting periods](basin-salt-balance.md#reporting-periods) for aggregation.

[Back to schema](basin-salt-balance.md).
