---
description: "Names of the other constituents, in a fixed order"
---

# cs

**Code reference:** `cs_db%cs` ([`declaration`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L28), [`read`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constit_db_read.f90#L63-L65)).

Enter the three names in this order: selenate, selenite, boron (for example `seo4 seo3 boron`).

SWAT+ identifies each one by its position, not its name ([`cs_sorb_hru.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_sorb_hru.f90#L73-L75)). The entered names are used to label solutes in groundwater (gwflow) solute transport ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1627-L1632)). Gwflow looks for a file literally named `constituents.cs` before including salts and these constituents, even if file.cio names another file ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1615-L1616)).
