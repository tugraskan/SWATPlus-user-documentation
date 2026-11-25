---
description: Time step of the simulation
---

# step

**Code reference:** `time%step` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_module.f90#L33)).

`step` is the number of simulation time steps per day (`steps/day`; Fortran struct default: `0`). In [`time_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_read.f90#L30), SWAT+ converts a value of `0` or any negative value to `1`, so both `0` and `1` produce a daily time step. In [`proc_bsn.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/proc_bsn.f90#L28), the sub-daily time-step length $\Delta t$ (`time%dtm`, minutes) is calculated as:

$$\Delta t = \frac{1440}{\text{step}}$$

where $\Delta t$ is the sub-daily time-step length (`time%dtm`, minutes) and $\text{step}$ is `step` (`steps/day`).

| Code | Time Step  |
| ---- | ---------- |
| 0 or 1 | day |
| 2    | 12 hours   |
| 24   | hour       |
| 96   | 15 minutes |
| 1440 | minute     |

{% hint style="warning" %}
When using the Green & Ampt method ([gampt](../../basin-1/codes.bsn/gampt.md) in [**codes.bsn**](../../basin-1/codes.bsn/)) for calculating surface runoff, the time step of the precipitation data must match the simulation time step.
{% endhint %}
