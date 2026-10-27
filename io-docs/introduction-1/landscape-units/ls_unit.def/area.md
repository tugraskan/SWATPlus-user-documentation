---
description: Area of the Landscape Unit in hectares
---

# area

**Code reference:** `lsu_out(i)%area_ha`

**Declared type:** `landscape_units` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/lsu_read_elements.f90#L70), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/calibration_data_module.f90#L195)).

Area of the Landscape Unit in hectares. When an LSU is included in a calibration region, SWAT+ multiplies this area by each HRU's fraction of the LSU to calculate that HRU's area in the region.
