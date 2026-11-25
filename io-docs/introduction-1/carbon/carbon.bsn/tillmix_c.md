---
description: "Clay exponent coefficient (c) of the maximum tillage mixing factor equation"
---

# tillmix\_c

**Code reference:** `tillmix_c` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/tillage_data_module.f90#L15), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_bsn_read.f90#L79), [calibration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L546-L547)).

Clay exponent coefficient $(c)$ in the equation [`mgt_tillfactor.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_tillfactor.f90#L62-L66) uses for tillage operations (originally fixed with constants $3$, $12$, and $-5.5$):

$$
z = a + b \, e^{c \cdot \text{clay} / 100}, \qquad F = z \, \frac{x}{x + e^{1 - 2x}}
$$

where:

- $z$ is the largest factor the layer can reach (dimensionless),
- $a$ is [tillmix\_a](tillmix_a.md) (dimensionless),
- $b$ is [tillmix\_b](tillmix_b.md) (dimensionless),
- $c$ is `tillmix_c` (dimensionless),
- $\text{clay}$ is the layer clay content (%),
- $F$ is the tillage mixing factor (dimensionless), and
- $x$ is the mixing effectiveness of the event plus the factor left from earlier events (dimensionless).

The biological and tillage factors are added, and with [idc\_till](../../basin-1/codes.bsn/idc_till.md) `= 3` decomposition is multiplied by $1 + F$ ([`cbn_zhang2.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cbn_zhang2.f90#L395-L398)).

The SWAT+ example file (`refdata/Ames_sub1`) heads this column `tillmix_c` and uses -3.5. The calibration parameter is `tillmix_c`.
