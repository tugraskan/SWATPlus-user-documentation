---
description: "Fraction of parent pesticide degradation in the foliar compartment that forms this daughter metabolite"
---

# foliar_fr

**Code reference:** `pestcp(ip)%daughter(imeta)%foliar_fr` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pesticide_data_module.f90#L30)).

Fraction (0–1) used for decay on foliage. The daughter mass is `parent mass decayed × fraction × (daughter mol_wt / parent mol_wt)` ([`pest_decay.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_decay.f90#L87-L96)).
