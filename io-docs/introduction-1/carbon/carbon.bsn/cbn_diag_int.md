---
description: "Flag that turns on the detailed soil carbon diagnostic output files"
---

# cbn\_diag\_int

**Code reference:** `cbn_diagnostics` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_module.f90#L5-L10), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_bsn_read.f90#L82), [conversion](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_bsn_read.f90#L93-L95)).

`1` turns on the detailed soil carbon diagnostic files; any other value leaves them off. It is the last value on the data line.

When a daily, monthly or yearly `hru_cb` switch in `print.prt` is on, the flag decides whether the beginning- and end-of-simulation soil property files (`hru_begsim_soil_prop`, `hru_endsim_soil_prop`) are opened ([`carbon_legacy_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_legacy_module.f90#L473-L516)) and written ([`soil_nutcarb_write_historical.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_write_historical.f90#L77-L78)). It also decides whether rows are written to `hru_plc_stat`, which is opened either way ([`soil_nutcarb_write_historical.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_write_historical.f90#L336-L339)).

{% hint style="info" %}
In SWAT+ main this setting came from the `hru_cb` row of `print.prt`. On dev the value in `carbon.bsn` is the only control ([`carbon_legacy_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_legacy_module.f90#L468-L470)).
{% endhint %}

The SWAT+ example file (`refdata/Ames_sub1`) heads this column `cbn_diagnostics`.
