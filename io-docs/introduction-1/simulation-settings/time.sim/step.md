---
description: Time step of the simulation
---

# step

**Code reference:** `time%step` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/time_module.f90#L34)).

`step` is the number of simulation time steps per day. SWAT+ converts a value of 0 or any negative value to 1, so both 0 and 1 produce a daily time step.

| Code | Time Step  |
| ---- | ---------- |
| 0 or 1 | day |
| 2    | 12 hours   |
| 24   | hour       |
| 96   | 15 minutes |
| 1440 | minute     |

{% hint style="warning" %}
When using the Green & Ampt method ([gampt](../../basin-1/codes.bsn/abstr_init.md) in [**codes.bsn**](../../basin-1/codes.bsn/)) for calculating surface runoff, the time step of the precipitation data must match the simulation time step.
{% endhint %}
