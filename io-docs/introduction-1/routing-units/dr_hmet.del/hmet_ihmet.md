---
description: "Heavy-metal delivery ratio associated with each simulated metal"
---

# hmet(ihmet)

**Code reference:** `dr_hmet(ii)%hmet(ihmet)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L59), [allocation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_read_hmet.f90#L49), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_read_hmet.f90#L64)).

Dimensionless delivery-ratio multiplier (`fraction`; Fortran allocation default: `0.`) for each simulated heavy metal $i = 1, \dots, N_{\text{metal}}$ (`cs_db%num_metals` from [`constituents.cs`](../../constituents/constituents.cs.md)). This file is read only when `cs_db%num_metals > 0` ([`dr_db_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_db_read.f90#L59)).

For standalone delivery-ratio (`dr`) spatial objects, [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L365) calls [`constit_hyd_mult.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constit_hyd_mult.f90#L29-L32), which scales each incoming heavy-metal load by:

$$M_{\text{out},i} = M_{\text{in},i} \cdot r_{i}$$

where $M_{\text{in},i}$ is `obcs(iob)%hin(1)%hmet(ihmet)`, $r_{i}$ is `dr_hmet(idr_hmet)%hmet(ihmet)`, and $M_{\text{out},i}$ is `obcs(iob)%hd(1)%hmet(ihmet)`. These heavy-metal delivery ratios are not applied to Routing Unit elements in [`ru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_control.f90#L124-L132).
