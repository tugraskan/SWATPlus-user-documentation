---
description: Salt-ion mass values in a salt-ion recall file
---

# salt(isalt)

**Code reference:** `rec_salt(i)%hd_salt(istep,iyrs)%salt(isalt)` ([allocation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_salt.f90#L134-L150), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_salt.f90#L200)).

Salt-ion mass load (`kg`; Fortran allocation default: `0.`) for each simulated salt ion $i = 1, \dots, N_{\text{salt}}$ (`cs_db%num_salts` from [`constituents.cs`](../../constituents/constituents.cs.md)).

During simulation, [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L355) calls [`recall_salt.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_salt.f90#L50-L110) to copy `rec_salt(irec)%hd_salt` into `obcs(icmd)%hd(1)%salt(isalt)` (or remove salt mass when daily `flo < 0` in [`recall_salt.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_salt.f90#L35-L46)). Note that [`recall_read_salt.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_salt.f90#L1-L248) is not called in SWAT+ main (`6f515368`).
