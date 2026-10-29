---
description: "Unmet groundwater pumping demand"
---

# pump_def

**Code reference:** `ppdf_grid` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_output.f90#L592)); `gw_hyd_grid_mo%ppdf` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_module.f90#L129)).

Groundwater pumping demand that could not be met. It is reported separately from the amount actually pumped and should not be counted as an additional withdrawal.

**Unit:** mm.

Daily unmet demand is normalized over total basin area. Monthly and yearly output sum the unmet demand; average-annual output gives the mean annual unmet demand over the reporting years.

[Back to the output table](README.md).
