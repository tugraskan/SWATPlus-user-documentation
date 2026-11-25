---
description: "1 = write daily exchange for this connection"
---

# obs

**Code reference:** `obs` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_chan_read.f90#L25), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_chan_read.f90#L66)).

Optional seventh field. A value above 0 adds the connection's cell to the daily outputs `gwflow_chan_obs_flow_day.txt` (exchange plus saturation-excess volume, m³) and, with solute transport, `gwflow_chan_obs_no3_day.txt` (nitrate mass, g) ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L660-L678), [`gwflow_simulate.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_simulate.f90#L240-L255)). These files are written when `print.prt` does not turn off the `gwflow_flux` output. It does not affect the simulation.
