---
description: "Recall temporal type code for general-constituent inputs"
---

# typ

**Code reference:** `rec_cs(i)%typ` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L244), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_cs.f90#L108)).

Integer temporal type code (Fortran default: `0`) controlling file reading in [`recall_read_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_cs.f90#L112-L233) and routing in [`recall_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_cs.f90#L31-L95):

* `1`: Daily time series (`hd_cs(366, nbyr)`). When the corresponding daily flow `flo < 0`, [`recall_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_cs.f90#L35-L46) removes constituent mass from the receiving channel via:

$$C_{\text{cs}} = \frac{1000\, M_{\text{ch}}}{V_{\text{ch}}}, \qquad M_{\text{div}} = \frac{C_{\text{cs}} \cdot Q_{\text{rec}}}{1000}$$

where $M_{\text{ch}}$ is `ch_water(ichan)%cs(ics)` (`kg`), $V_{\text{ch}}$ is `ch_stor(ichan)%flo` (`m^3`), $Q_{\text{rec}}$ is `recall(irec)%hd(time%day,time%yrs)%flo` (`m^3`, negative), and $-M_{\text{div}}$ is capped at $M_{\text{ch}}$.
* `2`: Monthly time series (`hd_cs(12, nbyr)`).
* `3`: Yearly time series (`hd_cs(1, nbyr)`).
* `4`: Constant / average-annual record ([`recall_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_cs.f90#L88-L95); [`recall_read_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_cs.f90#L112) skips opening a time-series file when `typ == 4`).

Although [`recall_read_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_cs.f90#L168-L196) includes `typ == 0` checks, it has no subdaily allocation branch (`#L128-L150`) and `recall_read_cs` is not called in SWAT+ main (`6f515368`).
