---
description: Average number of days of precipitation in month
---

# pcp\_days

**Code reference:** `wgn(iwgn)%pcpd(mo)` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/climate_module.f90#L38)).

This parameter is calculated as

$$
d_{wet,i}=\frac{days_{wet,i}}{yrs}
$$

where $$d_{wet,i}$$ is the average number of days of precipitation in month $$i$$, $$days_{wet,i}$$ is the number of wet days in month $$i$$ during the entire period of record, and $$yrs$$ is the number of years of record.
