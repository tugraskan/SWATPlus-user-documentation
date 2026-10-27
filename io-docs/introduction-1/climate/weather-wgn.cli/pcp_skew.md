---
description: Skew coefficient for daily precipitation in month
---

# pcp\_skew

**Code reference:** `wgn(iwgn)%pcpskw(mo)`

**Declared type:** `weather_generator_db` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/cli_wgnread.f90#L96), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/climate_module.f90#L35)).

This parameter quantifies the symmetry of the precipitation distribution around the monthly mean. The skew coefficient is calculated as

$$
g_{mon}=\frac{N*∑_{d=1}^N*(R_{day,mon}-R_{mon})^3 }{(N-1)*(N-2)*(σ_{mon})^3}
$$

where $$g_{mon}$$ is the skew coefficient for precipitation in the month, $$N$$ is the total number of daily precipitation records for month $$mon$$, $$R_{day,mon}$$ is the amount of precipitation for day $$d$$ in month $$mon$$ (mm H2O), $$R_{mon}$$ is the average precipitation for the month (mm H2O), and $$σ_{mon}$$ is the standard deviation for daily precipitation in month $$mon$$ (mm H2O). Daily precipitation values of 0 mm are included in the skew coefficient calculation.
