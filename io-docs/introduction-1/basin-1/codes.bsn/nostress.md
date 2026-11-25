---
description: Plant stress
---

# nostress

**Code reference:** `bsn_cc%nostress` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L38), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_cc.f90#L24)).

Controls whether plant growth stress factors are applied or overridden to `1.0` in [`pl_biomass_gro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_biomass_gro.f90#L107-L120) (struct default `0`).

| Code | Option |
| ---- | ------ |
| 0 | All plant stresses applied |
| 1 | Turn off all plant stress (`strsw`, `strst`, `strsn`, `strsp`, `strsa`, `strss` set to `1.0`) |
| 2 | Turn off nutrient plant stress only (`strsn` and `strsp` set to `1.0`) |
