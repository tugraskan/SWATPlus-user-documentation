---
description: "Storage drawdown time"
---

# ddown_days

**Code reference:** `canal(ic)%ddown_days` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/water_allocation_module.f90#L196)).

Controls the simple outflow calculation when [dtbl](dtbl.md) is `null`. Daily outflow is calculated as current canal storage divided by this value.
