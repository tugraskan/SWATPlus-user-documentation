---
description: Surface runoff lag time
---

# surq\_lag

**Code reference:** `bsn_prm%surlag` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L82), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L24)).

In large routing units with a time of concentration greater than 1 day, only a portion of the surface runoff reaches the main channel on the day it is generated (`days`, default `4`, range `1–24`; values `< 1.e-6` are reset to `4.0` in [`basin_prm_default.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_prm_default.f90#L11)).

In [`time_conc_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_conc_init.f90#L71-L74), `surq_lag` controls the fraction of stored surface runoff released each day ($f_{\text{rel}}$, with sub-daily simulations dividing $t_c$ by $\Delta t_{\min}/60$):

$$f_{\text{rel}} = 1 - \exp\!\left(-\frac{\text{surlag}}{t_c}\right)$$

where $f_{\text{rel}}$ is the daily released fraction of stored surface runoff (dimensionless), $\text{surlag}$ is `surq_lag` (`days`), and $t_c$ is the time of concentration (`hours`). For a given $t_c$, smaller *surq\_lag* values retain more water in surface storage and smooth the streamflow hydrograph.
