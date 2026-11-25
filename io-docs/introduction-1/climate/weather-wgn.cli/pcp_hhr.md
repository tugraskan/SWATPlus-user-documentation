---
description: Maximum 0.5-hour rainfall in month
---

# pcp\_hhr

**Code reference:** `wgn(iwgn)%rainhmx(mo)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/climate_module.f90#L39)).

This value represents the most extreme 30-minute rainfall depth recorded in the entire period of record.

The input is a rainfall depth in mm. SWAT+ averages the current and adjacent months, wrapping across December and January, then uses that average in estimating the peak half-hour rainfall fraction. The resulting fraction is bounded to $[0.10,0.95]$. See [cli_initwgn.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_initwgn.f90#L150-L156) and [cli_initwgn.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_initwgn.f90#L288-L300).
