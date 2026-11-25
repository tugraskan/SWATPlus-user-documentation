---
description: "Salt-ion export-coefficient loading for each simulated salt ion"
---

# salt(isalt)

**Code reference:** `exco_salt(ii)%salt(isalt)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L64), [allocation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_read_salt.f90#L48), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_read_salt.f90#L63)).

Constant salt-ion export-coefficient loading (`kg`; Fortran allocation default: `0.`) for each simulated salt ion $i = 1, \dots, N_{\text{salt}}$ (`cs_db%num_salts` from [`constituents.cs`](../../constituents/constituents.cs.md)). This file is read only when `cs_db%num_salts > 0` ([`exco_db_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_db_read.f90#L60)).

For each standalone `exco` spatial object whose [salts\_file](../exco.exc/salts_file.md) in [**exco.exc**](../exco.exc/README.md) is not `"null"` ([`exco_read_salt.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_read_salt.f90#L85)), [`exco_read_salt.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_read_salt.f90#L89) copies `exco_salt(iexco_salt)%salt` into `obcs(iob)%hd(1)%salt`.
