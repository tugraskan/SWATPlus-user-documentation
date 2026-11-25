---
description: "Sodium ion fraction"
---

# na

**Code reference:** `fert_salt(isalti)%na` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_module.f90#L58)).

Mass of sodium per mass of applied fertilizer or manure (kg/kg). The added load is `amount × fraction` (kg/ha), split between the top two soil layers by the application method ([`salt_fert.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_fert.f90#L49)). On ponded fields it goes to the water instead ([`salt_fert_wet.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_fert_wet.f90#L35)).
