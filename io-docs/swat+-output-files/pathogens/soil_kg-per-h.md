---
description: "Soil diagnostic with no identified producer"
---

# soil_kg/h

**Code reference:** `hpath_bal(j)%path(ipath)%soil` ([declaration/default](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_ls_pathogen_module.f90#L9)).

No active producer for this balance component was identified in the inspected source. It retains its declared zero default; it is not a verified report of the current soil pathogen pool. The actual process state is `cs_soil(j)%ly(1)%path(ipath)`, which is updated separately ([soil process](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/path_ls_process.f90#L60)).

At initialization, SWAT+ dev copies the configured soil entry into layer 1 and sets deeper layers to zero. (SWAT+ main cleared layer 1 again during every deeper-layer iteration.) [layer loop](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pathogen_init.f90#L74-L81).

**Unit:** unresolved. The printed heading says `kg/h`, the balance declaration says `kg/ha`, and the underlying constituent state is annotated `cfu`. The inspected code does not establish a consistent conversion between these bases; do not read the printed suffix as a verified per-hour rate.

Only `plant` and `soil` are assigned by the period-averaging operator. Averaging this unpopulated diagnostic does not establish a meaningful soil-storage report. The writer also lacks a yearly accumulator reset; see the [family table](README.md).

[Back to the output table](README.md).
