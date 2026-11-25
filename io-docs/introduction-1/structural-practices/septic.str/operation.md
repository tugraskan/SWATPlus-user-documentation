---
description: Septic system operation flag
---

# operation

**Code reference:** `sep(isep)%opt` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/septic_data_module.f90#L24)).

| Option | Description     |
| ------ | --------------- |
| 0      | Not operational |
| 1      | Active          |
| 2      | Failing         |

An active system automatically becomes failing as the biozone layer gets clogged over time. A failing system turns to an active system after the user specified number of days for rehabilitation defined by [t\_fail](t_fail.md).
