---
description: "Count of aquifers associated with the pipe"
---

# num_aqu

**Code reference:** `num_aqu / pipe(ipipe)%num_aqu` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L184), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_pipe_read.f90#L46,L53)).

Number of aquifer loss fractions listed at the end of the pipe row. The first read stores the value in local `num_aqu` ([`water_pipe_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_pipe_read.f90#L46)) to allocate `aqu_loss_fr` ([`water_pipe_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_pipe_read.f90#L50)), and the second read stores it in `pipe(ipipe)%num_aqu` ([`water_pipe_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_pipe_read.f90#L53)), which is not read during simulation.

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
