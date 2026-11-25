---
description: Target baseflow ratio for baseflow-mode soft calibration.
---

# bfr

**Code reference:** `lscal(ireg)%lum(ilum)%meas%bfr` ([read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lcu_read_softcal.f90#L89), [conversion](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lcu_read_softcal.f90#L94-L96)).

Dimensionless baseflow ratio (struct default `0.`). In `b`/`y` mode (`hyd_hru /= "a"`), supply the baseflow index:

$$\text{BFI} = \frac{Q_{\text{base}}}{Q_{\text{wyld}}}$$

where $\text{BFI}$ is the baseflow index (`bfr`, dimensionless), $Q_{\text{base}}$ is baseflow (`mm`), and $Q_{\text{wyld}}$ is total water yield (`mm`).

[`lcu_read_softcal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lcu_read_softcal.f90#L94-L96) converts it on read to the baseflow fraction of precipitation and derives `srr` and `lfr`:

$$f_{\text{bfr}}' = f_{\text{wyr}}\,f_{\text{bfr}}$$

where $f_{\text{bfr}}'$ is the converted baseflow fraction of precipitation (dimensionless), $f_{\text{wyr}}$ is `wyr` (dimensionless), and $f_{\text{bfr}}$ is the input `bfr` (dimensionless).

[`calsoft_hyd_bfr_perc.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_hyd_bfr_perc.f90#L46-L134) then calibrates `perco` against $f_{\text{bfr}}' P$.
