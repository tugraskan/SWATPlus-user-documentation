---
description: "Fraction of daily POU duty assigned to this POD"
---

# frac (POD)

**Code reference:** `pou(ipou)%pod(ipod)%frac` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L29), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L98)).

Dimensionless fraction of the POU's daily duty assigned to this POD (default: `0.`; the Fortran source comment erroneously lists `(m3/s)`). When [dtbl_pod_fr](dtbl_pod_fr.md) is `"null"`, [`wallo_start_day.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_start_day.f90#L182) computes:

$$D_{\text{pod}} = f_{\text{pod}} \cdot D_{\text{pou}}$$

where $f_{\text{pod}}$ is `frac` and $D_{\text{pou}}$ is `pou(ipou)%demand` (`m^3/day`). When `dtbl_pod_fr` is active, `frac` is overwritten daily by `trn_fr(ipod)` ([`wallo_start_day.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_start_day.f90#L174)). During withdrawal, `frac` also directly scales `unl` ([`wallo_withdraw.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_withdraw.f90#L48)) and `osrc` ([`wallo_withdraw.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_withdraw.f90#L55); there multiplied by the source rate × 86,400) withdrawals.
