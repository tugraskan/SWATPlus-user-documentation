---
description: "Selects the soil temperature factor equation for decomposition"
---

# tmpf

**Code reference:** `org_con%tmpf` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_module.f90#L117), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_bsn_read.f90#L76)).

Selects the soil temperature factor $f_T$ used for decomposition in [`cbn_zhang2.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cbn_zhang2.f90#L405-L422):

| Value | Factor |
| ----- | ------ |
| 1 | Logistic rise up to 35 °C, linear decline from 35 to 60 °C, and 0 above 60 °C |
| 2 | The function set by [tn](tn.md), [top](top.md) and [tx](tx.md) |
| 3 | Logistic curve with a 0.1 baseline |

For option `1`:

$$
f_T = \begin{cases} \dfrac{T}{T + e^{5.058 - 0.2504 T}}, & T \le 35 \\ 1 - 0.04\,(T - 35), & 35 < T \le 60 \\ 0, & T > 60 \end{cases}
$$

where $f_T$ is the soil temperature factor (dimensionless) and $T$ is the layer temperature (°C).

For option `3`:

$$
f_T = \frac{0.9 \, T}{T + e^{9.93 - 0.312 T}} + 0.1
$$

where $f_T$ and $T$ are as defined above.

Enter 1, 2 or 3. Any other value leaves $f_T$ unset, so the value from the previous layer or day is reused without a warning. Biological mixing ([`mgt_biomix.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_biomix.f90#L154-L165)) uses option 3 when this is 3 and option 2 otherwise. Decomposition runs only when the layer is above 0 °C and holds water ([`cbn_zhang2.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cbn_zhang2.f90#L334)).

The SWAT+ example file (`refdata/Ames_sub1`) heads this column `tmpf_eqn` and uses 2.
