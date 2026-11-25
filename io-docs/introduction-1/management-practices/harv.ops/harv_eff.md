---
description: Harvest efficiency
---

# harv\_eff

**Code reference:** `harvop_db(iharvop)%eff` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L114), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_harvops.f90#L44)).

Dimensionless harvest efficiency (`fraction`; default `0.0`, valid range `0.0–1.0`) controlling the fraction of harvested material exported from the HRU (`0.0` exports no yield; `1.0` exports all harvested yield). Its application depends on `harv_typ`:

**Biomass (`biomass`, `tree`, `stripper`):** Used in [`mgt_harvbiomass.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_harvbiomass.f90#L39-L42) to scale the harvest index:

$$HI_{\text{tot}} = HI_{\text{ovr}} \cdot E_{\text{harv}}$$

where $HI_{\text{tot}}$ is the effective harvest index (dimensionless), $HI_{\text{ovr}}$ is `harv_idx` (dimensionless), and $E_{\text{harv}}$ is `harv_eff` (dimensionless). The unharvested fraction $(1 - E_{\text{harv}}) \cdot Y$ is added to surface plant residue ([`mgt_harvbiomass.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_harvbiomass.f90#L112-L114)).

**Grain (`grain`, `picker`):** In [`mgt_harvgrain.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_harvgrain.f90#L40-L57), SWAT+ computes exported yield (before pest-stress scaling at line 51):

$$Y = E_{\text{harv}} \cdot M_{\text{seed}}$$

where $Y$ is exported grain yield (`kg/ha`), $E_{\text{harv}}$ is `harv_eff` (dimensionless), and $M_{\text{seed}}$ is seed biomass (`kg/ha`). The remainder $(1 - E_{\text{harv}}) \cdot M_{\text{seed}}$ is transferred into active soil humus `soil1(j)%hact(1)`.

**Tuber (`tuber`, `peanuts`):** In [`mgt_harvtuber.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_harvtuber.f90#L43-L46), SWAT+ computes exported yield (before pest-stress scaling at line 61):

$$Y = E_{\text{harv}} \cdot M_{\text{root}}$$

where $Y$ is exported tuber yield (`kg/ha`), $E_{\text{harv}}$ is `harv_eff` (dimensionless), and $M_{\text{root}}$ is root biomass (`kg/ha`).

**Residue (`residue`):** In [`mgt_harvresidue.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_harvresidue.f90#L46-L53), if the scheduled efficiency argument `harveff < 0.00001`, SWAT+ substitutes `harvop_db(iharvop)%eff` and multiplies it by `harv_idx`.
