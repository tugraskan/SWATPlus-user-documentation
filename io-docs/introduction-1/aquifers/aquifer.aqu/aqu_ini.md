---
description: Pointer to the aquifer constituent initialization record in initial.aqu_cs
---

# init

**Code reference:** `aqudb(i)%aqu_ini` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/aquifer_module.f90#L7)).

The init value is a foreign key matching the name field in initial.aqu_cs. SWAT+ uses that match to initialize pesticide and pathogen constituent data for the aquifer. It does not select a record from initial.aqu.
