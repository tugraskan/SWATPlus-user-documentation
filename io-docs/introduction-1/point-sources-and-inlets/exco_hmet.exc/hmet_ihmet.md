---
description: "Heavy-metal export-coefficient loading for each simulated metal"
---

# hmet(ihmet)

**Code reference:** `exco_hmet(ii)%hmet(ihmet)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L54), [allocation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_read_hmet.f90#L48), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_read_hmet.f90#L63)).

Constant heavy-metal export-coefficient loading (Fortran allocation default: `0.`) for each simulated heavy metal $i = 1, \dots, N_{\text{metal}}$ (`cs_db%num_metals` from [`constituents.cs`](../../constituents/constituents.cs.md)). This file is read only when `cs_db%num_metals > 0` ([`exco_db_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_db_read.f90#L59)).

For each standalone `exco` spatial object whose [hmet\_file](../exco.exc/hmet_file.md) in [**exco.exc**](../exco.exc/README.md) is not `"null"` ([`exco_read_hmet.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_read_hmet.f90#L86)), [`exco_read_hmet.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_read_hmet.f90#L90) copies `exco_hmet(iexco_hmet)%hmet` into `obcs(iob)%hd(1)%hmet`.
