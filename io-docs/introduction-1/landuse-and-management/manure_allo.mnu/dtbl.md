---
description: "Name of the decision table governing manure or fertilizer application"
---

# dtbl

**Code reference:** `mallo(imro)%trn(i)%dtbl` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/manure_allocation_module.f90#L46), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/manure_allocation_read.f90#L95)).

Character string (`len=25`, default `""`) acting as a foreign key referencing [name](../../decision-tables/lum.dtl/name.md) in [**lum.dtl**](../../decision-tables/lum.dtl/README.md) (or `"null"` to disable). Crosswalked against `dtbl_lum%name` in [`manure_allocation_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/manure_allocation_read.f90#L101-L112) and evaluated daily in [`mallo_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mallo_control.f90#L41-L47), where `manure_demand` actions populate source, rate, and method in [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L112-L123).
