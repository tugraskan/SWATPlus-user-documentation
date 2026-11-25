---
description: "Boundary type for this cell"
---

# bc_type_array(i)

**Code reference:** `bc_type_array(i)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L31), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L475-L477)).

Optional column 17. Boundary type of this cell; it replaces `bc_type` from [codes.gw](../codes.gw/bc_type.md) ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L475-L477)). It matters only when `stat` is 2: 2 means no flow to or from the cell, and any other value means a constant-head boundary that exchanges water with its neighbors ([`gwflow_lateral.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_lateral.f90#L61-L62)).
