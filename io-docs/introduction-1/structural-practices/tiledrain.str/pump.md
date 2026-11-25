---
description: Pump capacity
---

# pump

**Code reference:** `sdr(isdr)%pumpcap` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_module.f90#L93)).

Pump capacity in millimetres per hour (mm/hr; default `1.0`, range `0.0–10.0`). Used with the DRAINMOD equations (`tiledrain = 1` in `codes.bsn`, [`swr_drains.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/swr_drains.f90#L200-L201)) during subirrigation (negative drainage flux). When $|q| > P$, daily subirrigation flux is limited to:

$$q = -24 \cdot P$$

where $q$ is daily subirrigation flux (mm/day) and $P$ is `pump` (mm/hr). Note that in SWAT+ main (`6f515368`), the threshold comparison checks daily flux $|q|$ (mm/day) directly against `pump` (mm/hr) before multiplying by 24.
