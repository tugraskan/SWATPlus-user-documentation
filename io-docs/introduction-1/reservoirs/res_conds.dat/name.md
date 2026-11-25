---
description: "Record name"
---

# name

**Code reference:** `ctbl(ictbl)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_conditions_module.f90#L29)).

Primary key identifying each release condition table. In [`res_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read.f90#L121-L125), SWAT+ matches `name` against [rel](../reservoir.res/rel.md) in [**reservoir.res**](../reservoir.res/) whenever `rel` begins with `ctbl_`.
