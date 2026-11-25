---
description: Channel sinuosity
---

# sinu

**Code reference:** `sd_chd(idb)%sinu` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L29)).

Channel sinuosity (dimensionless, default `6.0`) is the ratio of channel length to straight-line distance between its endpoints. During initialization ([`sd_hydsed_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_hydsed_init.f90#L86-L87)), SWAT+ enforces a minimum of `1.05` (`if (sinu < 1.05) sinu = 1.05`).

In [`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/sd_channel_sediment3.f90#L180-L183), `sinu` determines the channel bend radius of curvature $R_c$ used to increase flow velocity in bends:

$$R_c = \frac{12\,w\,\text{sinu}^{1.5}}{13\,(\text{sinu} - 1)^{0.5}}$$

where $w$ is channel width (`wd`, m).

For rivers, the conventional classes of sinuosity are:

| Sinuosity       | Channel Form    |
| --------------- | --------------- |
| < 1.05          | almost straight |
| ≥ 1.05 - < 1.25 | winding         |
| ≥ 1.25 - < 1.50 | twisty          |
| ≥ 1.50          | meandering      |
