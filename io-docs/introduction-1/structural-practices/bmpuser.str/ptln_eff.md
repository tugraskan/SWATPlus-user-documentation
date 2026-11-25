---
description: Particulate N removal by BMP
---

# ptln\_eff

**Code reference:** `bmpuser_db(ibmpop)%bmp_pn` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L65)).

Enter the fraction of particulate nitrogen removed by this BMP (`0.0–1.0`; e.g., `0.2` removes 20%). In [`smp_bmpfixed.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/smp_bmpfixed.f90#L56), SWAT+ reduces organic nitrogen transported with sediment (`sedorgn`) by:

$$L_{\text{out}} = L_{\text{in}} \cdot (1 - E_{\text{pn}})$$

where $L_{\text{in}}$ and $L_{\text{out}}$ are sediment organic N before and after BMP removal, and $E_{\text{pn}}$ is `ptln_eff`.
