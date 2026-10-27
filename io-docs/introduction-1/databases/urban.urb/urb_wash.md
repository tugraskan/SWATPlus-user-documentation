---
description: Wash-off coefficient for removal of constituents from impervious surfaces
---

# urb\_wash

**Code reference:** `urbdb(iu)%urbcoef`

**Declared type:** `urban_db` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/urban_parm_read.f90#L42), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/urban_data_module.f90#L10)).

Wash off is the process of erosion or solution of constituents from an impervious surface during a runoff event. The original default value for urb\_wash was calculated as 0.18 mm-1 by assuming that 13 mm of total runoff in one hour would wash off 90% of the initial surface load (Huber and Heaney, 1982). Using sediment transport theory, Sonnen (1980) estimated values for the wash-off coefficient ranging from 0.002-0.26 mm-1. Huber and Dickinson (1988) noted that values between 0.039 and 0.390 mm-1 for the wash-off coefficient give sediment concentrations in the range of most observed values. This variable is used to calibrate the model to observed data.

#### References

> Huber and Dickinson (1988)
>
> Huber and Heaney (1982)
>
> Sonnen (1980)
