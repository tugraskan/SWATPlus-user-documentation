---
description: Irrigation application amount
---

# amt\_mm

**Code reference:** `irrop_db(irr_op)%amt_mm` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L7), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_irrops.f90#L48)).

Irrigation application amount (`mm`; table default `0.0`, Fortran derived-type initial `25.4`). SWAT+ uses `amt_mm` along three active pathways:

**Scheduled manual irrigation:** In [`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L361-L362) and [`#L574-L575`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L575-L576), SWAT+ computes applied water and irrigation runoff as:

$$I_{\text{app}} = A_{\text{mm}} \cdot E_{\text{irr}} \cdot (1 - f_{\text{surq}}), \qquad I_{\text{run}} = A_{\text{mm}} \cdot f_{\text{surq}}$$

where:
- $I_{\text{app}}$ is applied irrigation depth (`mm`),
- $I_{\text{run}}$ is irrigation runoff depth (`mm`),
- $A_{\text{mm}}$ is `amt_mm` (`mm`),
- $E_{\text{irr}}$ is `eff_frac` (dimensionless), and
- $f_{\text{surq}}$ is `sumq_frac` (dimensionless).

**Decision-table demand/transfer irrigation:** In [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L149-L150), SWAT+ uses:

$$I_{\text{app}} = A_{\text{mm}} \cdot E_{\text{irr}} \cdot (1 - f_{\text{surq}}), \qquad I_{\text{run}} = A_{\text{mm}} \cdot E_{\text{irr}} \cdot f_{\text{surq}}$$

where:
- $I_{\text{app}}$ is applied irrigation depth (`mm`),
- $I_{\text{run}}$ is irrigation runoff depth (`mm`),
- $A_{\text{mm}}$ is `amt_mm` (`mm`),
- $E_{\text{irr}}$ is `eff_frac` (dimensionless), and
- $f_{\text{surq}}$ is `sumq_frac` (dimensionless).

Direct `irrigate` decision-table actions at [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L275-L281) use the decision-table constant `d_tbl%act(iac)%const` instead of `amt_mm`.

**Paddy/wetland auto-irrigation:** In [`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L538-L539) and [`wet_irrp.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_irrp.f90#L28), `amt_mm` sets the maximum target ponding depth `hru(j)%irr_hmax`, and the minimum trigger depth `hru(j)%irr_hmin` is calculated as:

$$h_{\min} = 0.9\,h_{\max}$$

where $h_{\min}$ is the minimum ponding depth trigger (`mm`) and $h_{\max}$ is the maximum target ponding depth (`amt_mm`, `mm`).
