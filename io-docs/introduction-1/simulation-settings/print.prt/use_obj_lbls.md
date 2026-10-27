---
description: Controls whether print object rows are identified by label or fixed order
---

# use_obj_lbls

**Code reference:** `pco%use_obj_labels` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/basin_module.f90#L171)).

When use_obj_lbls is n, SWAT+ reads the object rows in the fixed order expected by the reader and ignores the first-column label. For any other value, SWAT+ matches each row by the object label in the first column. This field does not control database-format output.
