---
description: Ending year of the simulation
---

# yrc\_end

**Code reference:** `time%yrc_end` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_module.f90#L23)).

Ending calendar year of the simulation (`year`; Fortran struct default: `0`). Read in [`time_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_read.f90#L28-L32), it sets the total number of simulated years `time%nbyr`:

$$N_{\text{yr}} = y_{\text{end}} - y_{\text{start}} + 1$$

where $N_{\text{yr}}$ is `time%nbyr`, $y_{\text{start}}$ is `yrc_start`, and $y_{\text{end}}$ is `yrc_end`.

{% hint style="info" %}
If the simulation ends after the last day of the observed climate data, SWAT+ will use simulated climate data for the time period after the end of the observed climate data.
{% endhint %}
