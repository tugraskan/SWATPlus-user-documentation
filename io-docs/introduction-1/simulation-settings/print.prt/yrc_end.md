---
description: Calendar year to stop printing output (for daily printing only)
---

# yrc\_end

**Code reference:** `pco%yrc_end` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L162)).

Calendar year (`year`; Fortran struct default: `0`) to stop daily output printing. If set to `0`, [`basin_print_codes_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_print_codes_read.f90#L780) sets the stop year past the simulation end:

$$y_{\text{end,prt}} = y_{\text{start}} + N_{\text{yr}}$$

where $y_{\text{end,prt}}$ is `pco%yrc_end` (`year`), $y_{\text{start}}$ is `time%yrc` (`year`), and $N_{\text{yr}}$ is `time%nbyr` (`years`).

In [`time_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_control.f90#L199), `yrc_end` only controls `pco%day_print` (daily outputs) and does not affect monthly, yearly, or average-annual outputs.
