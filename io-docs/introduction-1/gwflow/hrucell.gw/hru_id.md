---
description: "HRU number"
---

# hru_id

**Code reference:** `hru_id` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L149), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L2165)).

HRU number. In the counting pass, numbers outside 1 to the number of HRUs are skipped ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L2138-L2145)). In the reading pass, lines are taken in order for HRU 1, 2, … ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L2159-L2165)), so a skipped number, or an HRU whose lines are not together, shifts the following lines to the wrong HRU. Keep the lines sorted by HRU.
