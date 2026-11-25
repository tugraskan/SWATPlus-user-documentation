---
description: "Record number"
---

# k

**Code reference:** `k` / index `i` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_elements.f90#L20-L21), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_elements.f90#L166-L169)).

Element index (`integer`, dimensionless, range `1..imax`) indexing `ccu_elem(i)` and referenced by [`elem_cnt`](../ch_catunit.def/elem_cnt.md) in [`ch_catunit.def`](../ch_catunit.def/README.md) and [`ch_reg.def`](../ch_reg.def/README.md).

*(Note: In SWAT+ main (6f515368), this column is parsed into memory and used only to index `ccu_elem` for unreferenced `ccu_out` and unread `ccu_cal` arrays).*
