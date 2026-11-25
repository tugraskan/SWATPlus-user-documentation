---
description: "Transport sub-steps per flow step"
---

# num_ts_transport

**Code reference:** `num_ts_transport` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L502), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1647)).

Number of transport sub-steps in each flow time step. The transport step is ([`gwflow_solute.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_solute.f90#L40-L43)):

$$\Delta t_{s} = \Delta t / n$$

where $\Delta t$ is `time_step` from [codes.gw](../codes.gw/time_step.md) and $n$ this value. Use a larger value when advection or dispersion makes concentrations oscillate. 0 makes the division fail.
