---
description: Number of columns to read for list of elements in the Routing Unit
---

# elem\_tot

**Code reference:** `nspu` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_read_elements.f90#L18), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_read_elements.f90#L118-L133)).

`elem_tot` specifies the number of integer tokens (`nspu`) read on the row for the Routing Unit's element list. If `nspu <= 0`, no element list is read and `ru_def(iru)%num_tot` is set to `0` ([`ru_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_read_elements.f90#L121-L123)).

If each element in the Routing Unit is listed individually, `elem_tot` equals the total number of elements. When consecutive element IDs are compressed using a negative range endpoint, `elem_tot` counts the tokens written on the row (which is smaller than the expanded element count `ru_def(iru)%num_tot` computed by [`define_unit_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/define_unit_elements.f90#L15-L48)).
