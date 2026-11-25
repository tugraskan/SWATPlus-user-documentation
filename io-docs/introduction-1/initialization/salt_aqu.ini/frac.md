---
description: "Salt mineral percentages at the start of the simulation"
---

# frac

**Code reference:** `salt_aqu_ini(isalt)%frac` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L305)).

Array of 5 initial aquifer salt mineral values (`CaCO3`, `MgCO3`, `CaSO4`, `MgSO4`, `NaCl`), allocated to size 5 and read in [`salt_aqu_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_aqu_read.f90#L49-L63). [`aqu_read_init_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_read_init_cs.f90#L122-L124) copies these values directly into `cs_aqu(iaq)%salt_min(1:5)`.

Although the field name `frac` and struct comment (`fractions`) imply dimensionless `0–1` fractions, [`salt_chem_aqu.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_chem_aqu.f90#L77-L82) and [`salt_balance.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_balance.f90#L363) divide `cs_aqu%salt_min` by `100.`, treating these inputs as **percent (`%`, `0–100`)** of aquifer solid mass.
