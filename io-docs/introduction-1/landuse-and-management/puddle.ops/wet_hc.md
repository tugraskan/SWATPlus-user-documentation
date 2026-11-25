---
description: "Hydraulic conductivity after puddling"
---

# wet\_hc

**Code reference:** `pudl_db(ic)%wet_hc` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L19), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_puddle.f90#L42)).

Effective hydraulic conductivity ($K_{\text{wet}}$, `mm/h`, struct default `0.0`) of the puddled upper soil layer beneath standing paddy/wetland water. When `wet_hc > 0`, puddling overwrites `hru(j)%wet_hc` ([`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L598), [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L972)); nonpositive values leave `hru(j)%wet_hc` unchanged. Daily wetland/paddy seepage $Q_{\text{seep}}$ (`m^3/d`) is then bounded by $K_{\text{wet}}$ in [`wetland_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wetland_control.f90#L105) (or converted to `m/d` in [`gwflow_wetland.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_wetland.f90#L65)):

$$Q_{\text{seep}} = \min\!\left(V_{\text{wet}},\; 240\,K_{\text{wet}}\,A_{\text{wet}}\right)$$

where $V_{\text{wet}}$ is standing water volume (`m^3`) and $A_{\text{wet}}$ is wetland surface area (`ha`).
