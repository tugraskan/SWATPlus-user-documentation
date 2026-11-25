---
description: Maximum amount of solids allowed to build up on impervious surfaces
---

# dirt\_max

**Code reference:** `urbdb(iu)%dirtmx` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/urban_data_module.f90#L11)).

**Current use:** solids built up on impervious surfaces after $t$ dry days are computed in [`hru_urban.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_urban.f90#L128-L144) as:

$$B = \frac{M\,t}{h + t}$$

where $B$ is built-up solids (`kg/curb km`), $M$ is `dirt_max` (`kg/curb km`), $t$ is dry days since the last wash-off (`days`), and $h$ is [t\_halfmax](t_halfmax.md) (`days`).
