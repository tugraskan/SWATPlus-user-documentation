---
description: Effective radius of drains
---

# rad

**Code reference:** `sdr(isdr)%radius` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_module.f90#L90)).

Effective radius of the subsurface drain tubes in millimetres (mm; default `30.0`, range `3.0–40.0`). Used with the DRAINMOD equations (`tiledrain = 1` in `codes.bsn`) in [`swr_drains.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/swr_drains.f90#L140-L141) to compute the Hooghoudt equivalent depth $d_e$ (mm) when $d / L < 0.3$:

$$d_e = \frac{d}{1 + \frac{d}{L}\left(\frac{8}{\pi}\ln\!\left(\frac{d}{r_e}\right) - \alpha\right)}$$

where $d$ is distance from the drain to the impermeable layer (mm), $L$ is drain spacing (`dist`, mm), $r_e$ is `rad` (mm), and $\alpha$ is a geometric shape factor dependent on $d/L$. It is also used in [Kirkham's equation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/swr_drains.f90#L149-L154) under surface-ponded conditions.
