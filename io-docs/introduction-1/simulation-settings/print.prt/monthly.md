---
description: Code for printing monthly output
---

# monthly

**Code reference:** `pco%<obj>%m` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L142)).

Character flag (`"y"` = yes, `"n"` = no; Fortran struct default: `"n"`) controlling monthly output for each object row in `print.prt` (after `nyskip` warm-up years).

For the legacy carbon rows `hru_cb` and `hru_cb_vars`, `"l"` writes the same monthly output as `"y"` plus per-layer rows ([`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L539-L558), [`soil_nutcarb_write_historical.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_write_historical.f90#L48-L70)). On SWAT+ main it also turned on the extra carbon diagnostic files; on dev those are controlled only by [cbn\_diag\_int](../../carbon/carbon.bsn/cbn_diag_int.md) in `carbon.bsn`. In GWFlow overrides, `gwflow_heat` and `gwflow_flux` do not enable output via the monthly column ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L292-L311)).
