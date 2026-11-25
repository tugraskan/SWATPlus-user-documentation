---
description: "Number of salt ions to simulate"
---

# num\_salts

**Code reference:** `cs_db%num_salts` ([`declaration`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L24), [`read`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constit_db_read.f90#L55-L58)).

Number of salt ions carried in the simulation. The default is 0, which turns salt simulation off. Use 0 or 8.

When it is above 0, the salt chemistry reads positions 1 to 8 of the ion list ([`hru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L248-L250), [`salt_chem_hru.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_chem_hru.f90#L157-L164)). A value from 1 to 7 is not rejected, but the chemistry then reaches past the end of the list. This is a suspected model defect.
