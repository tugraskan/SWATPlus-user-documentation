---
description: "Name of the referenced general-constituent initialization record"
---

# cs

**Code reference:** `aqu_init_dat_c_cs(iaqu)%cs` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aquifer_module.f90#L92)).

Foreign key referencing [name](../cs_aqu.ini/name.md) in [**cs\_aqu.ini**](../cs_aqu.ini/). When `cs_db%num_cs > 0`, [`aqu_read_init_cs.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/aqu_read_init_cs.f90#L131-L144) matches `aqu_init_dat_c_cs(iaq)%cs` positionally for aquifer `iaq` and initializes `cs_aqu(iaq)%csc`, `cs_aqu(iaq)%cs`, `cs_aqu(iaq)%csc_sorb`, and `cs_aqu(iaq)%cs_sorb`.
