---
description: "Nitrate nitrogen leaving with seepage"
---

# no3_seep

**Code reference:** `aqu_d(iaq)%no3_seep` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aquifer_module.f90#L51)).

Nitrate nitrogen transported out with seepage, expressed as nitrogen mass per unit area.

**Unit:** kg N/ha.

Daily output gives the daily exchange. Monthly and yearly output sum exchanges over the period. Average-annual output gives the mean annual total over the printed simulation years.

Basin output weights aquifer values by aquifer area relative to the total basin area.

The daily calculation uses the stored-nitrate component, which has initialization/allocation mass-basis inconsistencies; see [no3_st](no3_st.md). The kg N/ha label does not by itself certify numerical mass accounting in every configuration.

[Back to the output table](README.md).
