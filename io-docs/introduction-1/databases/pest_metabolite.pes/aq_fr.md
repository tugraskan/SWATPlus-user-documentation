---
description: "Fraction of parent pesticide degradation in the aquatic compartment that forms this daughter metabolite"
---

# aq_fr

**Code reference:** `pestcp(ip)%daughter(imeta)%aq_fr` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pesticide_data_module.f90#L32)).

Fraction (0–1) used for decay in channel water ([`ch_rtpest.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_rtpest.f90#L132-L139)). The daughter mass is `parent mass decayed × fraction × (daughter mol_wt / parent mol_wt)`. Reservoirs use [soil\_fr](soil_fr.md) instead.
