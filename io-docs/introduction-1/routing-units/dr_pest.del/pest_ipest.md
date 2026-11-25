---
description: "Pesticide delivery ratio associated with each simulated pesticide"
---

# pest(ipest)

**Code reference:** `dr_pest(ii)%pest(ipest)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L39), [allocation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_read_pest.f90#L48), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_read_pest.f90#L63)).

Dimensionless delivery-ratio multiplier (`fraction`; Fortran allocation default: `0.`) for each simulated pesticide $i = 1, \dots, N_{\text{pest}}$ (`cs_db%num_pests` from [`constituents.cs`](../../constituents/constituents.cs.md)). This file is read only when `cs_db%num_pests > 0` ([`dr_db_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_db_read.f90#L57)).

For standalone delivery-ratio (`dr`) spatial objects, [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L365) calls [`constit_hyd_mult.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constit_hyd_mult.f90#L19-L22), which scales each incoming pesticide mass by:

$$M_{\text{out},i} = M_{\text{in},i} \cdot r_{i}$$

where $M_{\text{in},i}$ is `obcs(iob)%hin(1)%pest(ipest)`, $r_{i}$ is `dr_pest(idr_pest)%pest(ipest)`, and $M_{\text{out},i}$ is `obcs(iob)%hd(1)%pest(ipest)`. These pesticide delivery ratios are not applied to Routing Unit elements in [`ru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_control.f90#L124-L132).
