---
description: "Daily channel depths by depth zone."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This optional file gives daily channel-water depths for the depth zones named by `dep_zone` in [chancell.gw](../chancell.gw/README.md). When it exists, these depths replace the channel's depth in groundwater–channel exchange.

SWAT+ looks for `chan_depth.gw` in the simulation working directory; it is not selected through `file.cio`. See the [`gwflow_chan_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_chan_read.f90#L86-L95) reader.

# chan_depth.gw

The first two lines are a title and column headings. Then give one line per simulated day: two date values, then one depth per depth zone. SWAT+ reads one line at the end of each day for the next day ([`gwflow_simulate.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_simulate.f90#L578-L581)); the dates are not checked. The first line is therefore used on the second day, and on the first day all depths are 0. This is listed in `MODEL_ISSUES.md`. Provide at least as many lines as simulated days minus one; reading past the end stops the run.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [jday](jday.md) | First date value; not used | integer | n/a | — | — |
| [year](year.md) | Second date value; not used | integer | n/a | — | — |
| [depth_by_zone](depth_by_zone.md) | Channel depth, one value per depth zone | real | m | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
