---
description: "Recall type selecting the temporal resolution for salt recall inputs"
---

# typ

**Code reference:** `rec_salt(i)%typ` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L232), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_salt.f90#L109)).

Integer temporal type code (Fortran default: `0`) controlling file reading in [`recall_read_salt.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_salt.f90#L113-L234) and routing in [`recall_salt.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_salt.f90#L31-L110):

* `1`: Daily time series (`hd_salt(366, nbyr)`). When the corresponding daily flow `flo < 0`, [`recall_salt.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_salt.f90#L35-L46) removes salt mass from the receiving channel via:

$$C_{\text{salt}} = \frac{1000\, M_{\text{ch}}}{V_{\text{ch}}}, \qquad M_{\text{div}} = \frac{C_{\text{salt}} \cdot Q_{\text{rec}}}{1000}$$

where $M_{\text{ch}}$ is `ch_water(ichan)%salt(isalt)` (`kg`), $V_{\text{ch}}$ is `ch_stor(ichan)%flo` (`m^3`), $Q_{\text{rec}}$ is `recall(irec)%hd(time%day,time%yrs)%flo` (`m^3`, negative), and $-M_{\text{div}}$ is capped at $M_{\text{ch}}$.
* `2`: Monthly time series (`hd_salt(12, nbyr)`).
* `3`: Yearly time series (`hd_salt(1, nbyr)`).
* `4`: Constant / average-annual record ([`recall_salt.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_salt.f90#L100-L110); [`recall_read_salt.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_salt.f90#L113) skips opening a time-series file when `typ == 4`).

Although [`recall_read_salt.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_salt.f90#L169-L197) includes `typ == 0` checks, it has no subdaily allocation branch (`#L129-L151`) and `recall_read_salt` is not called in SWAT+ main (`6f515368`).
