---
description: Half-life of the pesticide in the benthic sediment
---

# ben\_hlife

**Code reference:** `pestdb(ip)%ben_hlife` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pesticide_data_module.f90#L19)).

Half-life of the pesticide in benthic (bed) sediment, in days, applied in channels and reservoirs. Zero or less leaves nothing after one day ([`pest_parm_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_parm_read.f90#L74-L78)).

With [exp\_sed](../../basin-1/parameters.bsn/exp_sed.md) = 1 in parameters.bsn, channels adjust it by water temperature ([`ch_rtpest.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_rtpest.f90#L218-L224)); reservoirs do not ([`res_pest.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_pest.f90#L146-L150)).
