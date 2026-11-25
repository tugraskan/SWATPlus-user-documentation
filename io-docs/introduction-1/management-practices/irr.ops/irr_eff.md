---
description: Irrigation in-field efficiency
---

# eff\_frac

**Code reference:** `irrop_db(irr_op)%eff` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L8), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_irrops.f90#L48)).

Dimensionless irrigation in-field efficiency (`fraction`; default `0.0`, valid range `0.0–1.0`) representing the fraction of irrigation water available for land application rather than in-field application losses.

Across scheduled irrigation ([`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L361), [`#L574`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L575)), decision-table irrigation ([`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L149), [`#L253-L258`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L275-L280)), and paddy irrigation ([`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L532), [`wet_irrp.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_irrp.f90#L109-L110)), applied irrigation water is:

$$I_{\text{app}} = A \cdot E_{\text{irr}} \cdot (1 - f_{\text{surq}})$$

where $A$ is the gross irrigation depth (`mm`), $E_{\text{irr}}$ is `eff_frac`, and $f_{\text{surq}}$ is `sumq_frac`. Irrigation runoff also multiplies by $E_{\text{irr}}$ in [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L150) and [`wet_irrp.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_irrp.f90#L110), whereas [`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L362) and [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L277-L281) compute runoff directly as $A \cdot f_{\text{surq}}$.
