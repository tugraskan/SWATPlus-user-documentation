---
description: Number of years of maximum monthly 0.5 h rainfall data
---

# yrs\_pcp

**Code reference:** `wgn(iwgn)%rain_yrs` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/climate_module.f90#L28)).

SWAT+ reads a real number of years and replaces values below 1 with 10. It uses $0.5/Y$ in estimating the peak half-hour fraction, where $Y$ is the resulting record length. The [pcp_hhr](pcp_hhr.md) input is read separately. See [cli_initwgn.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_initwgn.f90#L289-L300).
