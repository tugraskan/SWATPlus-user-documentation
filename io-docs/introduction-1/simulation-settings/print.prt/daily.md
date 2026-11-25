---
description: Code for printing daily output
---

# daily

**Code reference:** `pco%<obj>%d` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L141)).

Character flag (`"y"` = yes, `"n"` = no; Fortran struct default: `"n"`) controlling daily output for each object row in `print.prt`. Daily printing is additionally gated by `nyskip`, `day_start`, `yrc_start`, `day_end`, `yrc_end`, and `interval`.

For the legacy carbon rows `hru_cb` and `hru_cb_vars`, `"l"` writes the same daily output as `"y"` plus per-layer rows ([`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L539-L558), [`soil_nutcarb_write_historical.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_write_historical.f90#L48-L70)). On SWAT+ main it also turned on the extra carbon diagnostic files; on dev those are controlled only by [cbn\_diag\_int](../../carbon/carbon.bsn/cbn_diag_int.md) in `carbon.bsn`. For `gwflow_pump` and `gwflow_flux`, this column acts as part of a group switch rather than an independent daily toggle ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L286-L311)).
