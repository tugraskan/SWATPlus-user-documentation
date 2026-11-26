---
description: Harvest type
---

# harv\_typ

**Code reference:** `harvop_db(iharvop)%typ` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L112), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_harvops.f90#L44)).

Character keyword (`len=40`) selecting which harvest physics routine SWAT+ dispatches via `select case (harvop_db(iharvop)%typ)` in [`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L166-L183) / [`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L278-L294) and [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L542-L559) / [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L658-L674):

| Harvest type | Description | Routine |
| ------------ | ----------- | ------- |
| `grain` | Grain harvest | [`mgt_harvgrain.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_harvgrain.f90#L1-L83) |
| `biomass` | Harvest of above-ground biomass | [`mgt_harvbiomass.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_harvbiomass.f90#L1-L138) |
| `residue` | Harvest of surface residue | [`mgt_harvresidue.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_harvresidue.f90#L1-L86) |
| `tuber` | Harvest of roots/tubers | [`mgt_harvtuber.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_harvtuber.f90#L1-L110) |
| `peanuts` | Harvest of roots/tubers | [`mgt_harvtuber.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_harvtuber.f90#L1-L110) |
| `tree` | Harvest of above-ground biomass | [`mgt_harvbiomass.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_harvbiomass.f90#L1-L138) |
| `stripper` | Harvest of above-ground biomass | [`mgt_harvbiomass.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_harvbiomass.f90#L1-L138) |
| `picker` | Grain harvest | [`mgt_harvgrain.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_harvgrain.f90#L1-L83) |
