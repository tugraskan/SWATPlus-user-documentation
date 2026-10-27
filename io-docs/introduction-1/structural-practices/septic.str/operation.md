---
description: ​Septic system operation flag
---

# operation

**Code reference:** `sep(isep)%opt`

**Declared type:** `septic_system` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/sep_read.f90#L43), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/septic_data_module.f90#L24)).

| Option | Description     |
| ------ | --------------- |
| 0      | Not operational |
| 1      | Active          |
| 2      | Failing         |

An active system automatically becomes failing as the biozone layer gets clogged over time. A failing system turns to an active system after the user specified number of days for rehabilitation defined by [t\_fail](t_fail.md).&#x20;
