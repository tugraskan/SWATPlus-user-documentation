---
description: "Selects the soil water factor equation for decomposition"
---

# watf

**Code reference:** `org_con%watf` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_module.f90#L118), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_bsn_read.f90#L76)).

Selects the soil water factor $f_W$ used for decomposition in [`cbn_zhang2.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cbn_zhang2.f90#L341-L368):

| Value | Factor |
| ----- | ------ |
| 1 | Square-root soil water function (limited to 0.05–1), defined below |
| 2 | Product of a water-content term (0.4 at wilting point rising to 1 at field capacity) and an air-filled pore term |

For option `1`:

$$
f_W = 0.1 + 0.9 \sqrt{SW / FC}
$$

where $f_W$ is the soil water factor (dimensionless, limited to 0.05–1), $SW$ is the layer soil water content (mm), and $FC$ is the layer field capacity (mm).

Enter 1 or 2. Any other value leaves $f_W$ unset, so the value from the previous layer or day is reused without a warning.

The SWAT+ example file (`refdata/Ames_sub1`) heads this column `watf_eqn` and uses 1.
