---
description: Soil phosphorus model
---

# soil\_p

**Code reference:** `bsn_cc%sol_p_model` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L63), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_cc.f90#L24)).

Selects the inorganic soil phosphorus initialization and mineralization routine in [`soil_nutcarb_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_init.f90#L76-L100) and [`hru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L408-L412) (struct default `0`).

| Code | Option |
| ---- | ------ |
| 0 | Original soil phosphorus model (`nut_pminrl`) |
| 1 | Vadas and White (2010) soil phosphorus model (`nut_pminrl2`) |
