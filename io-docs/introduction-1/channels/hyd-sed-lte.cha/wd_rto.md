---
description: Channel sinuosity
---

# sinu

**Code reference:** `sd_chd(idb)%sinu` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L29)).

Channel sinuosity (dimensionless, default `6.0`) is the ratio of channel length to straight-line distance between its endpoints. During initialization ([`sd_hydsed_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_hydsed_init.f90#L86-L87)), SWAT+ enforces a minimum of `1.05` (`if (sinu < 1.05) sinu = 1.05`).

On SWAT+ dev, `sinu` (at least 1.05) sets a bend factor $b = \text{sinu}^{0.38}$ (1.3 when `sinu` exceeds 2), and the reach velocity for bank erosion is $0.33\, b + 0.66\, v$ ([`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L209-L238)). The SWAT+ main radius-of-curvature calculation below no longer exists:

$$R_c = \frac{12\,w\,\text{sinu}^{1.5}}{13\,(\text{sinu} - 1)^{0.5}}$$

where $w$ is channel width (`wd`, m).

For rivers, the conventional classes of sinuosity are:

| Sinuosity       | Channel Form    |
| --------------- | --------------- |
| < 1.05          | almost straight |
| ≥ 1.05 - < 1.25 | winding         |
| ≥ 1.25 - < 1.50 | twisty          |
| ≥ 1.50          | meandering      |
