---
description: ID of the element
---

# id (rout\_unit.ele)

**Code reference:** `i`, `k` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_read_elements.f90#L20-L23), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_read_elements.f90#L49-L71)).

The ID of the element is a primary key referenced by [elements](../untitled-1/elements.md) in [**rout\_unit.def**](../untitled-1/). During input parsing, `id` directly indexes the `ru_elem(i)` array (`1` to the maximum ID in the file), so all IDs in **rout\_unit.ele** must be positive and unique.
