---
description: Recall temporal type code selecting subdaily, daily, monthly, yearly, or EXCO behavior
---

# type

**Code reference:** `recall(i)%typ` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L430), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L80)).

Integer temporal type code (Fortran default: `0`; valid values `0`–`4`) controlling array allocation in [`recall_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L96-L110) and routing in [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L320-L347):

* `0`: Subdaily time series. Allocates `recall(i)%hyd_flo(time%step*366, time%nbyr)` and `recall(i)%hd(366, time%nbyr)`. Each input flow rate $Q_{\text{in}}$ (`m^3/s`) is converted to subdaily step volume (`m^3`) via [`recall_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L151) and accumulated into daily `recall(i)%hd` ([`recall_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L158-L160)):

$$Q_{\text{step}} = \frac{86400\, Q_{\text{in}}}{N_{\text{step}}}$$

where $N_{\text{step}}$ is `time%step` (subdaily steps per day).
* `1`: Daily time series (`recall(i)%hd(366, time%nbyr)`). If daily flow `flo < 0`, [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L330-L331) treats the record as a diversion and invokes [`recall_nut.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_nut.f90#L2-L88) to remove solute mass from the downstream channel.
* `2`: Monthly time series (`recall(i)%hd(12, time%nbyr)`), applied each day of the matching month within `[start_yr, end_yr]`.
* `3`: Yearly time series (`recall(i)%hd(1, time%nbyr)`). Note that [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L343) uses an `.or.` condition (`time%yrc >= start_yr .or. time%yrc <= end_yr`), so the year guard evaluates true for all simulation years.
* `4`: Export-coefficient (constant) record. Skips opening a time-series file and instead copies `exco(iexco_om)` into `recall(i)%hd(1,1)` when `exco_db(iexco_om)%name == recall(i)%filename` ([`recall_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L182-L191)). Note that [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L320-L347) has no `case (4)` branch for `recall` objects, while water-allocation routines fall through to `exco(iom)`.
