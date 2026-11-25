---
description: General-constituent mass values in a general-constituent recall file
---

# cs(ics)

**Code reference:** `rec_cs(i)%hd_cs(istep,iyrs)%cs(ics)` ([allocation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_cs.f90#L133-L149), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_cs.f90#L199)).

General-constituent mass load (`kg`; Fortran allocation default: `0.`) for each simulated constituent $i = 1, \dots, N_{\text{cs}}$ (`cs_db%num_cs` from [`constituents.cs`](../../constituents/constituents.cs.md)).

During simulation, [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L356) calls [`recall_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_cs.f90#L50-L95) to copy `rec_cs(irec)%hd_cs` into `obcs(icmd)%hd(1)%cs(ics)` (or remove constituent mass when daily `flo < 0` in [`recall_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_cs.f90#L35-L46)). Note that [`recall_read_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_cs.f90#L1-L247) is not called in SWAT+ main (`6f515368`).
