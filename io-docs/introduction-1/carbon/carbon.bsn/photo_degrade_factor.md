---
description: "Daily fraction of surface residue lost to photodegradation"
---

# photo\_degrade\_factor

**Code reference:** `photo_degrade_factor` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L7), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_bsn_read.f90#L80), [calibration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L491-L492)).

Fraction of each plant's surface residue (mass, carbon, nitrogen and phosphorus) that [`cbn_surfrsd_decomp.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/cbn_surfrsd_decomp.f90#L72-L79) removes each day by photodegradation. The removed carbon is reported as a residue carbon emission.

The SWAT+ example file (`refdata/Ames_sub1`) heads this column `sfc_rsd_photodeg` and uses 0.001. The calibration parameter is `sfc_rsd_photodeg`.
