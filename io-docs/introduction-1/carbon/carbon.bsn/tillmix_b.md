---
description: "Multiplier of the clay term (b) of the maximum tillage mixing factor equation"
---

# tillmix\_b

**Code reference:** `tillmix_b` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/tillage_data_module.f90#L14), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_bsn_read.f90#L79), [calibration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L544-L545)).

Multiplier of the clay term $(b)$ in the equation [`mgt_tillfactor.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_tillfactor.f90#L62-L66) uses for tillage operations (originally fixed with constants $3$, $12$, and $-5.5$):

$$
z = a + b \, e^{c \cdot \text{clay} / 100}, \qquad F = z \, \frac{x}{x + e^{1 - 2x}}
$$

where:

- $z$ is the largest factor the layer can reach (dimensionless),
- $a$ is [tillmix\_a](tillmix_a.md) (dimensionless),
- $b$ is `tillmix_b` (dimensionless),
- $c$ is [tillmix\_c](tillmix_c.md) (dimensionless),
- $\text{clay}$ is the layer clay content (%),
- $F$ is the tillage mixing factor (dimensionless), and
- $x$ is the mixing effectiveness of the event plus the factor left from earlier events (dimensionless).

The biological and tillage factors are added, and with [idc\_till](../../basin-1/codes.bsn/idc_till.md) `= 3` decomposition is multiplied by $1 + F$ ([`cbn_zhang2.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cbn_zhang2.f90#L395-L398)).

The SWAT+ example file (`refdata/Ames_sub1`) heads this column `tillmix_b` and uses 15.0. The calibration parameter is `tillmix_b`.
