---
description: "Delivery ratio for each simulated pathogen"
---

# path(ipath)

**Code reference:** `dr_path(ii)%path(ipath)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L49), [allocation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_path_read.f90#L48), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_path_read.f90#L63)).

Dimensionless delivery-ratio multiplier (`fraction`; Fortran allocation default: `0.`) for each simulated pathogen $i = 1, \dots, N_{\text{path}}$ (`cs_db%num_paths` from [`constituents.cs`](../../constituents/constituents.cs.md)). This file is read only when `cs_db%num_paths > 0` ([`dr_db_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_db_read.f90#L58)).

For standalone delivery-ratio (`dr`) spatial objects, [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L365) calls [`constit_hyd_mult.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constit_hyd_mult.f90#L24-L27), which scales each incoming pathogen load by:

$$M_{\text{out},i} = M_{\text{in},i} \cdot r_{i}$$

where $M_{\text{in},i}$ is `obcs(iob)%hin(1)%path(ipath)`, $r_{i}$ is `dr_path(idr_path)%path(ipath)`, and $M_{\text{out},i}$ is `obcs(iob)%hd(1)%path(ipath)`. These pathogen delivery ratios are not applied to Routing Unit elements in [`ru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_control.f90#L124-L132).
