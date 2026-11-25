---
description: Organic nitrogen load in an organic/mineral recall file
---

# orgn

**Code reference:** `recall(i)%hd%orgn` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L34), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L158-L171)).

Organic nitrogen load (`kg N`; Fortran default: `0.`). Read into `recall(i)%hd` and routed to `ob(icmd)%hd(1)` in [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L325-L344).

When daily `flo < 0` (`type = 1`), [`recall_nut.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_nut.f90#L68-L81) instead computes channel-diverted organic nitrogen mass from channel storage and zeroes `ob(icmd)%hd(1)%orgn` (`#L81`):

$$C_{\text{sol}} = \frac{1000\, M_{\text{ch}}}{V_{\text{ch}}}, \qquad M_{\text{div}} = \frac{C_{\text{sol}} \cdot Q_{\text{rec}}}{1000}$$

where $M_{\text{ch}}$ is `ch_stor(ichan)%orgn` (`kg N`), $V_{\text{ch}}$ is `ch_stor(ichan)%flo` (`m^3`), $Q_{\text{rec}}$ is `recall(irec)%hd(time%day,time%yrs)%flo` (`m^3`, negative), and $-M_{\text{div}}$ is capped at $M_{\text{ch}}$.
