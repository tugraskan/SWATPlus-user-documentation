---
description: USLE slope length and slope factor LS
---

# usle\_ls

**Code reference:** `hlt_db(i)%uslels`

**Declared type:** `swatdeg_hru_data` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hru_lte_read.f90#L117), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hru_lte_module.f90#L50)).

SWAT+ main (6f515368) calculates the LS factor from slp and slp_len when it reads the HRU-lte data. That calculation overwrites the entered usle_ls value, so changing this input currently has no effect.
