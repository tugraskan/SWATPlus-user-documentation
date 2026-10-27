---
description: Per-capita septic tank effluent flow rate (read but not used by the model)
---

# q\_rate

**Code reference:** `sepdb(is)%qs`

**Declared type:** `septic_db` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/septic_parm_read.f90#L48), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/septic_data_module.f90#L7)).

McCray et al. (2005) proposed 0.227 m3/capita/day as the median value for the United States based on the data collected from various sources.

#### References

> McCray et al. (2005)

SWAT+ main (6f515368) reads this value from `septic.sep` but does not use it in model calculations.
