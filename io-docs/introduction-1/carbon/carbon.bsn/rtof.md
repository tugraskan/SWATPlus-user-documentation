---
description: "Weighting factor that splits the organic N and P of applied fertilizer and manure between pools"
---

# rtof

**Code reference:** `man_coef%rtof` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_module.f90#L79), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_bsn_read.f90#L74), [calibration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L485-L486)).

Weighting factor for the organic nitrogen and phosphorus in applied fertilizer and manure. With carbon `= 2`, the share $1 - r$ goes to the slow humus pool: [`pl_manure.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_manure.f90#L109-L114) for manure and [`pl_fert.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_fert.f90#L111-L116) for organic fertilizer. The source comment still describes septic effluent, which does not match this use.

For organic fertilizer, [`pl_fert.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_fert.f90#L118-L125) also uses $1 - r$, not $r$, for the metabolic and structural litter pools, although the source comment says `rtof`. The amount added is then $2(1 - r)$ times the applied organic matter, which equals the applied amount only when $r = 0.5$. For manure, all of the organic nitrogen also goes to the metabolic and structural litter pools ([`pl_manure.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_manure.f90#L137-L142)), so $(2 - r)$ times the applied organic nitrogen is added. Both are listed in `MODEL_ISSUES.md`.

The SWAT+ example file (`refdata/Ames_sub1`) heads this column `manure_c_frac` and uses 0.5. The calibration parameter is `manure_c_frac`.
