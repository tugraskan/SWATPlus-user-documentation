---
description: USLE slope length and slope factor LS
---

# usle\_ls

**Code reference:** `hlt_db(i)%uslels` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_module.f90#L50)).

SWAT+ main (6f515368) calculates the LS factor from [slp](slp.md) and [slp\_len](slp_len.md) when it reads the HRU-lte data ([`hru_lte_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_read.f90#L237-L242)). That calculation overwrites the entered usle\_ls value, so changing this input currently has no effect.

$$m = 0.6 \left( 1 - e^{-35.835 \, s} \right)$$

where $m$ is the slope-length exponent (dimensionless) and $s$ is the slope ([slp](slp.md), `m/m`).

$$LS = \left( \frac{L}{22.128} \right)^{m} \left( 65.41 \sin^2 a + 4.56 \sin a + 0.065 \right)$$

where $LS$ is the calculated USLE slope length and slope factor (dimensionless), $L$ is the slope length ([slp\_len](slp_len.md), `m`), $m$ is the slope-length exponent, and $a$ is the slope angle ($\arctan s$).
