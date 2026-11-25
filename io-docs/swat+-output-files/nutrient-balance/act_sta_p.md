---
description: "Signed mineral-P exchange: positive active to stable; negative stable to active"
---

# act_sta_p

**Code reference:** `hnb_d(j)%act_sta_p` in the HRU record ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_output.f90#L73)); matching component in basin and LSU records.

The output accumulates the signed `roc` transfer. Positive values represent active-to-stable mineral P; negative values represent the reverse direction. See the [pool updates and assignment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/nut_pminrl.f90#L44) and the [alternative routine](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/nut_pminrl2.f90#L139). Monthly and yearly records accumulate these contributions; average-annual records divide them by printed years.

**Unit:** kg P/ha.

In `nut_pminrl2`, the diagnostic is incremented after a conditional block that can suppress the pool updates when total P is at least 10,000 mg/kg. A reported calculated transfer is therefore not proof of an equal pool-mass change on that path; compare the [conditional updates and subsequent reporting](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/nut_pminrl2.f90#L152).

[Back to the output table](README.md).
