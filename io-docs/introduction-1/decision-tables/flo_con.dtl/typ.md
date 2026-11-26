---
description: "Flow-control action type"
---

# typ

**Code reference:** `dtbl_flo(i)%act(iac)%typ` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditional_module.f90#L17)).

Action type. The type must suit the input that selects the table:

| Type | Used by | Effect | Source |
| ---- | ------- | ------ | ------ |
| `wallo_dmd` | `dtbl_mx` | Sets the day's water demand (m³) according to [option](option.md) | [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L190-L240) |
| `duty_fr` | `dtbl_pod_fr`, `dtbl_por_fr` | Sets the fraction for one source or receiver | [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L833-L858) |
| `tileflo_control` | saturated buffer | Sets how much tile flow goes to the buffer HRU | [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L861-L889) |
| `duty_reset` | no automatic caller: the table named by [pod_dtbl_wdraw](../../water-allocation/place_of_use.wro/pod_dtbl_wdraw.md) is never evaluated | Sets a source's maximum withdrawal | [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L183-L187) |

The flow-control reader does not look up database records, so field operations from `lum.dtl` should not be entered here. [`dtbl_flocon_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dtbl_flocon_read.f90#L64-L69)
