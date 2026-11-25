---
description: Precipitation and temperature lapse rate control
---

# lapse

**Code reference:** `bsn_cc%lapse` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L50), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_cc.f90#L24)).

Enables or disables elevation-based precipitation and temperature lapse adjustments computed in [`cli_lapse.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_lapse.f90#L18-L35) and invoked from [`hru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L126-L132), [`res_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_control.f90#L50), and [`sd_channel_control3.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_control3.f90#L108) (struct default `0`).

| Code | Option |
| ---- | ------ |
| 0 | Do not adjust precipitation and temperature for elevation |
| 1 | Adjust precipitation and temperature for elevation |

When `lapse = 1`, adjustments use [plaps](../parameters.bsn/plaps.md) and [tlaps](../parameters.bsn/tlaps.md) in [**parameters.bsn**](../parameters.bsn/).
