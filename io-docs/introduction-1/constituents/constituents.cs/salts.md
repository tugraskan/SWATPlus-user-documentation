---
description: "Names of the simulated salt ions, in a fixed order"
---

# salts

**Code reference:** `cs_db%salts` ([`declaration`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L25), [`read`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constit_db_read.f90#L57-L59)).

Enter the eight ions in this order: sulfate, calcium, magnesium, sodium, potassium, chloride, carbonate, bicarbonate (for example `so4 ca mg na k cl co3 hco3`).

SWAT+ identifies each ion by its position, not its name ([`salt_chem_hru.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_chem_hru.f90#L157-L164)). Changing the order changes which values the chemistry treats as each ion, and salt output labels stay in the order above. The entered names are used to label solutes in groundwater (gwflow) solute transport ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1617-L1622)).
