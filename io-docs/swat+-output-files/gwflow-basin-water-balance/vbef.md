---
description: "Groundwater storage at the before-solution checkpoint"
---

# vbef

**Code reference:** `vbef_grid` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L154)).

Groundwater storage at the simulator's before-solution checkpoint, summed over active cells and converted to an equivalent depth over the full basin area.

The simulator computes cell `vbef` from current head, bottom elevation, area, and specific yield at the start of its lateral-solution section. This follows several exchange calculations; channel and other exchange routines can already have changed groundwater heads. The value is therefore not assured to be untouched start-of-day storage ([checkpoint](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_simulate.f90#L305); [example earlier head update](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_channel_exch.f90#L101)).

**Unit:** mm.

This field appears in the daily file only; it is not a column in the monthly, yearly, or average-annual basin water-balance files.

[Back to the daily basin water-balance schema](daily-basin-water-balance.md).
