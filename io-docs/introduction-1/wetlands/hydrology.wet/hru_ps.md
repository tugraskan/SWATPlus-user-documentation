---
description: Fraction of HRU area at principal spillway
---

# hru\_ps

**Code reference:** `wet_hyddb(ires)%psa` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/reservoir_data_module.f90#L84)).

The fraction of HRU area at principal spillway is multiplied with the HRU area to calculate the principal surface area in ha. However, this value is only used for estimating the initial wetland area. For daily wetland simulations, the model assumes for simplicity that the entire HRU is wet, so the HRU area is used instead of the principal surface area to calculate the principal volume of the wetland. Accordingly, the parameter hru\_ps has very limited impact on wetland calculations.
