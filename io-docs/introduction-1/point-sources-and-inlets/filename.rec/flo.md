---
description: Water flow in an organic/mineral recall file
---

# flo

**Code reference:** `recall(i)%hd%flo` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L32), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L151-L171)).

Water volume or discharge rate (Fortran default: `0.`). For `type = 1`, `2`, or `3` in [`recall.rec`](../recall.rec/README.md), values are read directly as daily water volume (`m^3`) without conversion ([`recall_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L164-L171), [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L325-L344)). For subdaily records (`type = 0`), input values in `m^3/s` are converted to subdaily step volume (`m^3`) and summed into daily `recall(i)%hd` ([`recall_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L151-L160)):

$$Q_{\text{step}} = \frac{86400\, Q_{\text{in}}}{N_{\text{step}}}$$

where $Q_{\text{in}}$ is the input flow rate (`m^3/s`) and $N_{\text{step}}$ is `time%step`.

For daily records (`type = 1`), negative `flo` values indicate a diversion from the downstream channel rather than an inflow: [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L330-L331) calls [`recall_nut.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_nut.f90#L28-L81), [`recall_salt.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_salt.f90#L35-L46), and [`recall_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_cs.f90#L35-L46) to remove solute mass from the receiving channel, and [`gwflow_simulate.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_simulate.f90#L195) reads `-flo` as canal diversion volume.
