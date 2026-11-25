---
description: Potential evapotranspiration multiplier
---

# pet\_co

**Code reference:** `hyd_db(ithyd)%pet_co` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrology_data_module.f90#L50)).

Dimensionless multiplier for daily potential evapotranspiration. [`et_pot.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/et_pot.f90#L273-L280) applies it after the method selection, including when PET is read from a weather file:

$$PET_{\mathrm{out}} = c \, PET_{\mathrm{base}}$$

where $PET_{\mathrm{out}}$ is the adjusted HRU potential evapotranspiration (mm/day), $c$ is `pet_co` (dimensionless), and $PET_{\mathrm{base}}$ is the potential evapotranspiration computed by the selected method (mm/day).

During HRU initialization, values below $10^{-6}$ become 1. Values from $10^{-6}$ up to but excluding 0.01 are divided by 0.0023 to support legacy `harg_pet` inputs. Other values are used as entered. [`topohyd_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/topohyd_init.f90#L73-L81)
