---
description: "Saturation-excess connection-event count divided by active-cell count"
---

# sat_frac

**Code reference:** `frac_sat = real(satx_count) / real(num_active)` ([output calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L890)).

The numerator is incremented each time the saturation-excess routine processes a qualifying active channel-cell connection with groundwater head above the surface. It is not an independent scan of every active cell's saturation status ([counter update](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_satexcess.f90#L38)).

**Unit:** fraction.

The reader counts cells with `stat > 0` for the denominator. That includes active cells (`stat = 1`) and boundary cells (`stat = 2`). The numerator only counts qualifying connections to active cells. The ratio can exceed 1 if qualifying events outnumber the cells counted in the denominator. [Cell count](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L531), [Cell statuses](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L61)

The output does not deduplicate cell IDs before forming this ratio. Whether the event count also represents unique cells depends on the connection lists and calls; do not assume it is a unique-cell fraction or an area-weighted saturated fraction. The counter is reset after daily output in the simulator ([reset](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_simulate.f90#L503)).

This field appears only in the daily basin file, not monthly, yearly, or average annual.

[Back to the daily basin water-balance schema](daily-basin-water-balance.md).
