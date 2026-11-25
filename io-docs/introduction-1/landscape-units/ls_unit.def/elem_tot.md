---
description: Number of columns to read for list of elements in the Landscape Unit
---

# elem\_tot

**Code reference:** `nspu` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lsu_read_elements.f90#L17), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lsu_read_elements.f90#L65)).

Number of integer tokens read into `elem_cnt(1:nspu)` on this row (`integer`, dimensionless, valid range `>= 0`, default `0`). When elements are listed individually, `elem_tot` equals the number of elements in the Landscape Unit; when a contiguous block is entered as `start -end`, that range uses two tokens (`elem_tot = 2`).

SWAT+ expands the `nspu` tokens in [`define_unit_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/define_unit_elements.f90#L1-L96) and stores the expanded element list and total element count in `lsu_out(i)%num` and `lsu_out(i)%num_tot` ([`lsu_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lsu_read_elements.f90#L76-L77)).
