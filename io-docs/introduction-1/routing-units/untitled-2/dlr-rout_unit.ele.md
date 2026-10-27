---
description: Delivery ratio name or calculation keyword for the element
---

# dlr

**Code reference:** `ru_elem(i)%dr_name` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hydrograph_module.f90#L493)).

The `dlr` field controls the delivery ratio applied to the element's hydrograph. Enter the name of an entry in `delratio.del` to use that delivery-ratio data. Enter `full` or `1` to use a delivery ratio of 1.0. Enter `calc` or `0` to calculate a time-of-concentration ratio for an HRU or HRU-LTE element; for an `sdc` or nested `ru` element, this option uses 1.0.
