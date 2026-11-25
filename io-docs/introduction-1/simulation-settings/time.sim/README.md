---
description: This file controls the simulation time period and time step.
---

# time.sim

This file is read by [`time_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_read.f90#L28).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [day\_start](day_start.md) | Beginning day of the simulation | integer | day |  |  |
| [yrc\_start](yrc_start.md) | Beginning year of the simulation | integer | year |  |  |
| [day\_end](day_end.md) | Ending day of the simulation | integer | day |  |  |
| [yrc\_end](yrc_end.md) | Ending year of the simulation | integer | year |  |  |
| [step](step.md) | Time step of the simulation | integer | steps/day |  |  |
