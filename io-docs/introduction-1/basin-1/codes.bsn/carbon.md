---
description: Carbon routine
---

# carbon

**Code reference:** `bsn_cc%cswat` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L44), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_cc.f90#L24)).

Selects the soil organic carbon and residue decomposition routine in [`hru_control.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hru_control.f90#L385-L402) (struct default `0`). In SWAT+ main (`6f515368`), option `1` (C-FARM) is reserved and not implemented; only `0` and `2` execute.

| Code | Option |
| ---- | ------ |
| 0 | Static soil carbon (standard mineralization routines) |
| 1 | C-FARM one carbon pool model (reserved, not implemented in main `6f515368`) |
| 2 | Dynamic CENTURY/SWAT-C model |

When `carbon = 2`, SWAT+ requires [**carbon.bsn**](../../carbon/carbon.bsn/) ([`carbon_bsn_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_bsn_read.f90#L47-L55)) and uses [idc\_till](idc_till.md) to select the tillage mixing formulation.
