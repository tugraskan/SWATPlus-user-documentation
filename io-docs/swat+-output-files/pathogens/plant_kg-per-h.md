---
description: "Plant diagnostic initialized from input; not refreshed from foliage"
---

# plant_kg/h

**Code reference:** `hpath_bal(ihru)%path(ipath)%plant = path_soil_ini(ipath_db)%plt(ipath)` ([initialization](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pathogen_init.f90#L83)).

This balance component receives the plant entry from the selected initialization record. The initializer puts that entry only in the output diagnostic and starts the live `cs_pl%pl_on%path` array at zero. Wash-off and net die-off or regrowth later change the live state. Do not interpret this diagnostic as current foliage pathogen storage. [initialization](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/pathogen_init.f90#L56-L79), [foliage updates](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/path_ls_process.f90#L38-L58).

**Unit:** unresolved. The printed heading says `kg/h`, the balance declaration says `kg/ha`, and the underlying constituent state is annotated `cfu`. The inspected code does not establish a consistent conversion between these bases; do not read the printed suffix as a verified per-hour rate.

Monthly output averages this diagnostic over calendar-month days. The yearly writer averages monthly diagnostics using 12, but does not reset its yearly accumulator afterward. Average-annual values inherit that carry-over issue. See the [family table](README.md) for layout and CSV limitations.

[Back to the output table](README.md).
