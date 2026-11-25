---
description: "Maximum storage capacity of the water tower"
---

# stor_mx

**Code reference:** `wtow(iwtow)%stor_mx` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L181), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_tower_read.f90#L42)).

Maximum storage capacity of the water tower (`m^3`; uninitialized in the derived-type definition). Used in flow-control decision tables ([flo_con.dtl](../../decision-tables/flo_con.dtl/README.md)).

For condition `wtow_vol` ([`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L738)), SWAT+ compares `wtow_om_stor(iwtow)%flo` against the threshold volume:

$$V_{\text{targ}} = c_{\text{lim}} \cdot V_{\max}$$

where $V_{\text{targ}}$ is the threshold volume ($\text{m}^3$), $c_{\text{lim}}$ is the condition limit multiplier, and $V_{\max}$ is `stor_mx` (`m^3`).

For action `fill_wtow` ([`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L228-L230)), SWAT+ computes refill demand (`m^3`):

$$D_{\text{m3}} = \max\!\left(0,\, \left(c_1 \cdot V_{\max} - V_{\text{stor}}\right) \cdot c_2\right)$$

where:

- $D_{\text{m3}}$ is the refill demand ($\text{m}^3$)
- $V_{\max}$ is `wtow(j)%stor_mx` (`m^3`)
- $V_{\text{stor}}$ is `wtow_om_stor(j)%flo` (`m^3`)
- $c_1$ is `const` from the action
- $c_2$ is `const2` from the action
