---
description: Crack flow code
---

# crack

**Code reference:** `bsn_cc%crk`

**Declared type:** `basin_control_codes` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/basin_read_cc.f90#L24), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/basin_module.f90#L25)).

| Code | Option                            |
| ---- | --------------------------------- |
| 0    | Do not compute crack flow in soil |
| 1    | Compute crack flow in soil        |

If crack = 1, the crack volume potential is controlled by [perc\_crk](../../soils/soils.sol/perc_crk.md) in [**soils.sol**](../../soils/soils.sol/).
