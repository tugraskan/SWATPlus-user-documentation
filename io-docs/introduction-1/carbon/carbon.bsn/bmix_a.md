---
description: "Base value (a) of the maximum biological mixing factor equation"
---

# bmix\_a

**Code reference:** `bmix_a` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/tillage_data_module.f90#L10), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_bsn_read.f90#L78), [calibration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L536-L537)).

Base value $(a)$ in the equation [`mgt_tillfactor.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_tillfactor.f90#L59-L61) uses for biological mixing events (originally fixed with constants $3$, $5$, and $-5.5$):

$$
z = a + b \, e^{c \cdot \text{clay} / 100}, \qquad F = z \, \frac{x}{x + e^{1 - 2x}}
$$

where:

- $z$ is the largest factor the layer can reach (dimensionless),
- $a$ is `bmix_a` (dimensionless),
- $b$ is [bmix\_b](bmix_b.md) (dimensionless),
- $c$ is [bmix\_c](bmix_c.md) (dimensionless),
- $\text{clay}$ is the layer clay content (%),
- $F$ is the biological mixing factor (dimensionless), and
- $x$ is the mixing effectiveness of the event plus the factor left from earlier events (dimensionless).

The biological and tillage factors are added, and with [idc\_till](../../basin-1/codes.bsn/idc_till.md) `= 3` decomposition is multiplied by $1 + F$ ([`cbn_zhang2.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cbn_zhang2.f90#L395-L398)).

The SWAT+ example file (`refdata/Ames_sub1`) heads this column `bmix_a` and uses 3.0. The calibration parameter is `bmix_a`.
