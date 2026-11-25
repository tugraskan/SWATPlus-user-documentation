---
description: Dissolved oxygen load in an organic/mineral recall file
---

# dox

**Code reference:** `recall(i)%hd%dox` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L42), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L158-L171)).

Dissolved oxygen load (`kg`; Fortran default: `0.`). Read into `recall(i)%hd` and routed to `ob(icmd)%hd(1)` in [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L325-L344).

When daily `flo < 0` (`type = 1`), [`recall_nut.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_nut.f90#L60-L65) instead removes dissolved oxygen mass from channel storage and [`recall_nut.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_nut.f90#L80) zeroes `ob(icmd)%hd(1)%dox`:

$$C_{\text{sol}} = \frac{1000\, M_{\text{ch}}}{V_{\text{ch}}}, \qquad M_{\text{div}} = \frac{C_{\text{sol}} \cdot Q_{\text{rec}}}{1000}$$

where $M_{\text{ch}}$ is `ch_stor(ichan)%dox` (`kg`), $V_{\text{ch}}$ is `ch_stor(ichan)%flo` (`m^3`), $Q_{\text{rec}}$ is `recall(irec)%hd(time%day,time%yrs)%flo` (`m^3`, negative), and $-M_{\text{div}}$ is capped at $M_{\text{ch}}$.
