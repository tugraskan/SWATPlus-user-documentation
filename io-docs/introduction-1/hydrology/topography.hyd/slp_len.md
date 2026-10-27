---
description: Average slope length
---

# slp\_len

**Code reference:** `topo_db(ith)%slope_len`

**Declared type:** `topography_db` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/topo_read.f90#L51), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/topography_data_module.f90#L8)).

The average slope length describes the distance that sheet flow is the dominant surface runoff flow process. It should be measured to the point where flow begins to concentrate. It is easily observable after a heavy rain on a fallow field when the rills are well developed. In this situation, the slope length is the distance from the micro-watershed divide to the origin of the rill. The average slope length can also be determined from topographic maps.&#x20;

The average slope length is used to compute soil erosion using the MUSLE.
