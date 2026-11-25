---
description: Instream nutrient routing method
---

# qual2e

**Code reference:** `bsn_cc%qual2e` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L68), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_cc.f90#L24)).

Controls instream nutrient transformations in [`sd_channel_control3.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_control3.f90#L203-L220) (struct default `0`). `ch_watqual4` (QUAL2E) always runs; when `qual2e = 1`, SWAT+ subsequently applies a simplified exponential inorganic-to-organic N and P transformation override using channel partitioning parameters (`n_sol_part` and `p_sol_part`).

| Code | Option |
| ---- | ------ |
| 0 | Instream nutrient routing using QUAL2E |
| 1 | Instream nutrient routing using QUAL2E with simplified nutrient transformation override |
