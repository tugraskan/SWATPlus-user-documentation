---
description: "Record number"
---

# k

**Code reference:** `k` / index `i` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read_elements.f90#L20-L21), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read_elements.f90#L162-L165)).

Element index (`integer`, dimensionless, range `1..imax`) indexing `rcu_elem(i)` and referenced by [`elem_cnt`](../res_catunit.def/elem_cnt.md) in [`res_catunit.def`](../res_catunit.def/README.md) and [`res_reg.def`](../res_reg.def/README.md).

*(Note: In SWAT+ main (6f515368), this column is parsed into memory and used only to index `rcu_elem` for unused `rcu_out` and unread `rcu_cal` arrays).*
