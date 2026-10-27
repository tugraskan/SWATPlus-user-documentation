---
description: Controls whether print object rows are identified by label or fixed order
---

# use_obj_lbls

Called `use_obj_labels` in the Fortran code.

When use_obj_lbls is n, SWAT+ reads the object rows in the fixed order expected by the reader and ignores the first-column label. For any other value, SWAT+ matches each row by the object label in the first column. This field does not control database-format output.
