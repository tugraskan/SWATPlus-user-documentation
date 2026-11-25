---
description: Aeration stress factor
---

# aeration

**Code reference:** `pldb(ic)%aeration` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L94)).

Aeration-stress threshold $a$, a fraction of the pore space between field capacity and saturation. Values of zero or less are replaced by 0.2 ([`plantparm_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plantparm_init.f90#L29)). Stress starts when the filled fraction $s$ of that space exceeds $a$ ([`pl_waterup.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_waterup.f90#L82-L89)):

$$x = 100\,\frac{s - a}{1.0001 - a}, \qquad f = 1 - \frac{x}{x + \exp(2.9014 - 0.03867x)}$$

where $x$ is the scaled excess-water index (dimensionless), $s$ is the filled fraction of pore space between field capacity and saturation (dimensionless), $a$ is `aeration` (dimensionless), and $f$ is the aeration stress factor (dimensionless; `1` = no stress).
