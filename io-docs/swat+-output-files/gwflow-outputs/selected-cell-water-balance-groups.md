# Selected-Cell GWFlow Water-Balance Groups

With GWFlow enabled, add `gwflow.wbgroups` to produce daily group files. The reader expects a title line, the number of groups, and the maximum number of cells in a group. Each group then has a label line, a cell count, and one cell ID per line. Use valid positive IDs from the [cell definition file](cell-definition.md). The file is opened without a `gwflow_wb` or `gwflow_flux` switch. The filename is `gwflow_group_wb_day_` plus an `I2` group number, with space padding and no added `.txt` suffix. [Group reader and opener](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L133-L179).

Each file has 30 fields in the order of the [daily basin schema](../gwflow-basin-water-balance/daily-basin-water-balance.md) with `sat_frac` omitted. Water quantities are in m³, `error` is a percentage, and `wt_depth` is in m. The `unit` and `gis_id` fields both contain `1`, and `name` contains the basin name. Group identity comes from the filename and configuration.

Storage and flux values sum the daily diagnostics of the listed active cells (`stat == 1`). Each listed occurrence is counted, so duplicate IDs count twice. For the 16 fluxes also printed in the [individual cell file](cell-water-balance.md), the group value is the sum of the signed daily cell diagnostics before rounding. `pump_def` reports unmet pumping demand separately. The `error` formula uses `100 × (1 − (vbef + signed fluxes) / vaft)`, excludes `pump_def`, and divides by `vaft` without checking for zero. [Group calculation and writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L749-L815), [daily cell writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1223-L1241).

{% hint style="warning" %}
The group-depth calculation resets its sum inside the per-cell loop. With valid positive IDs, it uses the last listed cell's depth if that cell is active, or zero if it is inactive, then divides by the configured group size. For example, a group listing two active cells with depths of 4 m and 10 m reports 5 m. Reversing the list reports 2 m.
{% endhint %}

[Back to the GWFlow Outputs index](README.md).
