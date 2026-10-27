---
description: Potential evapotranspiration (PET) method
---

# pet

**Code reference:** `bsn_cc%pet`

**Declared type:** `basin_control_codes` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/basin_read_cc.f90#L24), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/basin_module.f90#L20)).

Numerous methods exist to calculate potential evapotranspiration. Three of the most widely-used ones are included in SWAT+, the Priestley-Taylor, Penman/Monteith, and Hargreaves equations. The codes for the three methods are listed in the table below. If a method other than Priestley-Taylor, Penman/Monteith, or Hargreaves is recommended for the area, in which the watershed is located, the user can calculate daily PET values with the recommended method and import them into SWAT+ (using [pet](../../climate/weather-sta.cli/pet.md) in [**weather-sta.cli**](../../climate/weather-sta.cli/)).&#x20;

| Code | Option                  |
| ---- | ----------------------- |
| 0    | Priestley-Taylor method |
| 1    | Penman/Monteith method  |
| 2    | Hargreaves method       |
