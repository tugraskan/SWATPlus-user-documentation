---
description: "Pesticide export-coefficient loading for each simulated pesticide"
---

# pest(ipest)

**Code reference:** `exco_pest(ii)%pest(ipest)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L34), [allocation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_read_pest.f90#L47), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_read_pest.f90#L62)).

Constant pesticide export-coefficient loading (`mg`; Fortran allocation default: `0.`) for each simulated pesticide $i = 1, \dots, N_{\text{pest}}$ (`cs_db%num_pests` from [`constituents.cs`](../../constituents/constituents.cs.md)). This file is read only when `cs_db%num_pests > 0` ([`exco_db_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_db_read.f90#L57)).

For each standalone `exco` spatial object whose [pest\_file](../exco.exc/pest_file.md) in [**exco.exc**](../exco.exc/README.md) is not `"null"` ([`exco_read_pest.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_read_pest.f90#L85)), [`exco_read_pest.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_read_pest.f90#L89) copies `exco_pest(iexco_pest)%pest` into `obcs(iob)%hd(1)%pest`.
