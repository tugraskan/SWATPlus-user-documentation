---
description: "Names of the simulated pathogens"
---

# paths

**Code reference:** `cs_db%paths` ([`declaration`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L19), [`read`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constit_db_read.f90#L44-L46)).

One name per pathogen. Enter [num\_paths](num_paths.md) names. Their order is the order of pathogen values in other input files.

SWAT+ looks up each name in [pathogens.pth](../../databases/pathogens.pth/README.md), but the result is not used afterwards ([`constit_db_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constit_db_read.f90#L79-L86)). HRU processes instead take the pathogens.pth record whose position equals the position of the HRU's record in [path\_hru.ini](../../initialization/path_hru.ini/README.md) ([`hru_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_read.f90#L101-L106), [`path_ls_runoff.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/path_ls_runoff.f90#L20-L24)), and channel routing takes the record at the pathogen's position in this list ([`ch_rtpath.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_rtpath.f90#L80-L90)). This is a suspected model defect; until it is resolved, check that those positions select the intended pathogens.
