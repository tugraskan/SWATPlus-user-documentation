---
description: "Fraction of parent pesticide degradation in the soil compartment that forms this daughter metabolite"
---

# soil_fr

**Code reference:** `pestcp(ip)%daughter(imeta)%soil_fr` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pesticide_data_module.f90#L31)).

Fraction (0–1) used for decay in soil ([`pest_decay.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_decay.f90#L59-L65)) and aquifers ([`aqu_1d_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L328-L334)). Reservoirs also use it for both water and bed-sediment decay ([`res_pest.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_pest.f90#L79-L85), [`res_pest.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_pest.f90#L152-L158)). The daughter mass is `parent mass decayed × fraction × (daughter mol_wt / parent mol_wt)`.
