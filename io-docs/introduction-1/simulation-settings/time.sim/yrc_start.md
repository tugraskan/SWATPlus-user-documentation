---
description: Beginning year of the simulation
---

# yrc\_start

**Code reference:** `time%yrc_start` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_module.f90#L22)).

Beginning calendar year of the simulation (`year`; Fortran struct default: `0`). Read in [`time_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_read.f90#L28-L43), it initializes the current simulation calendar year `time%yrc` and determines the total number of simulated years in [`time_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_read.f90#L32):

$$N_{\text{yr}} = y_{\text{end}} - y_{\text{start}} + 1$$

where $N_{\text{yr}}$ is `time%nbyr`, $y_{\text{start}}$ is `yrc_start`, and $y_{\text{end}}$ is `yrc_end`.

{% hint style="info" %}
If the simulation begins before the first day of the observed climate data, SWAT+ will use simulated climate data for the time period before the start of the observed climate data.
{% endhint %}
