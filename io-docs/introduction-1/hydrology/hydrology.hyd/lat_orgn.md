---
description: Organic nitrogen concentration in lateral flow
---

# lat\_orgn

**Code reference:** `hyd_db(ithyd)%lat_orgn` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrology_data_module.f90#L48)).

Organic nitrogen concentration $C$ in lateral flow, in mg/L. The built-in value is 0. [`swr_latsed.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/swr_latsed.f90#L49-L52) adds $q_{\ell}C/10^4$ to the sediment-associated organic N load, where $q_{\ell}$ is lateral flow depth in mm. The calculation excludes tile flow.

The source uses a divisor of $10^4$, which is 100 times larger than the divisor for a direct conversion from mm and mg/L to kg/ha. This is flagged as a suspected unit-conversion issue.
