---
description: "Record type of an outputs.gw line"
---

# record_type

**Code reference:** `split_fields(1)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L185), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L607)).

Record type, written exactly as shown (lower case):

* `observation_cell`: the value is a cell to report in the observation output.
* `head_output_time`: older type; the date is stored but produces no output.
* `detail_debug_cell`: older type; the cell number is stored but not used.

Other text is skipped without a message ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L607-L618)).
