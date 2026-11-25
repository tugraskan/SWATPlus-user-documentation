---
description: "Write average annual GWFlow balance output (1 = on)"
---

# write_aa

**Code reference:** `gwflag_aa` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L12), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L257)).

1 writes the average annual basin and cell water-balance output; 0 does not. Heat and solute balances follow the same setting ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L273-L276)).

If `print.prt` has a `gwflow_wb` row, that row replaces all four `write_*` settings; `gwflow_heat` and `gwflow_solute` rows likewise control the heat and solute balances ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L263-L306)).
