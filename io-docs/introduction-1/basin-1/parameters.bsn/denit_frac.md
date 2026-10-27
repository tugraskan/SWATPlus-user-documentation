---
description: Denitrification threshold as a fraction of field capacity
---

# denit\_frac

**Code reference:** `bsn_prm%sdnco` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/basin_module.f90#L112)).

This parameter defines the fraction of field capacity water content above which denitrification takes place. Denitrification is the bacterial reduction of nitrate (NO3) to N2 or N2O gases under anaerobic (reduced) conditions. Because SWAT+ does not track the redox status of the soil layers, the presence of anaerobic conditions in a soil layer is defined by this variable. If the soil water content calculated as a fraction of field capacity is ≥ _denit\_frac_, then anaerobic conditions are assumed to be present and denitrification is modeled. If the soil water content calculated as a fraction of field capacity is < _denit\_frac_, then aerobic conditions are assumed to be present and denitrification is not modeled.
