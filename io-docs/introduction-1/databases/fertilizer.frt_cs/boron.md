---
description: "Boron constituent mass fraction"
---

# boron

**Code reference:** `fert_cs(icsi)%boron` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_module.f90#L66)).

Mass of boron per mass of applied fertilizer or manure (kg/kg). The added load is `amount × fraction` (kg/ha), put in the top soil layer ([`cs_fert.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_fert.f90#L47)). On ponded fields it goes to the water instead ([`cs_fert_wet.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_fert_wet.f90#L34)).
