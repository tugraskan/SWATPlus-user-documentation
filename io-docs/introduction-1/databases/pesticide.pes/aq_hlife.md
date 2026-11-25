---
description: >-
  Half-life of the pesticide in water
---

# aq\_hlife

**Code reference:** `pestdb(ip)%aq_hlife` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pesticide_data_module.f90#L12)).

Half-life of the pesticide in water, in days, applied in channels, reservoirs and aquifers. Zero or less leaves nothing after one day ([`pest_parm_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_parm_read.f90#L69-L73)).

With [exp\_sed](../../basin-1/parameters.bsn/exp_sed.md) = 1 in parameters.bsn, SWAT+ adjusts it for temperature in channels ([`ch_rtpest.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_rtpest.f90#L123-L128)) and aquifers ([`aqu_1d_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L320-L326)), but not in reservoirs ([`res_pest.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_pest.f90#L75)).
