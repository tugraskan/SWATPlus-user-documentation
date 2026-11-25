---
description: Soluble N removal by BMP
---

# soln\_eff

**Code reference:** `bmpuser_db(ibmpop)%bmp_sn` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L66)).

Enter the fraction of soluble nitrogen removed by this BMP (`0.0–1.0`; e.g., `0.2` removes 20%). In [`smp_bmpfixed.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/smp_bmpfixed.f90#L58-L59), SWAT+ reduces both surface runoff nitrate (`surqno3`) and lateral flow nitrate (`latno3`) by:

$$L_{\text{out}} = L_{\text{in}} \cdot (1 - E_{\text{sn}})$$

where $L_{\text{in}}$ and $L_{\text{out}}$ are the nitrate load before and after BMP removal, and $E_{\text{sn}}$ is `soln_eff`.
