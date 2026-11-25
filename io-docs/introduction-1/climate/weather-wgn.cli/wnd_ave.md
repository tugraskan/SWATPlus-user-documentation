---
description: Average daily wind speed in month
---

# wnd\_ave

**Code reference:** `wgn(iwgn)%windav(mo)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/climate_module.f90#L42)).

This value is calculated by summing the average or mean wind speed values for every day in the month for all years of record and dividing the sum by the number of days:

$$
μwnd_{mon}=\frac{∑_{d=1}^N*T_{wnd,mon}}{N}
$$

where $μwnd_{mon}$ is the mean daily wind speed for the month (m/s), $T_{wnd,mon}$ is the average wind speed for day $d$ in month $mon$ (m/s), and $N$ is the total number of daily wind speed records for month $mon$.

The wind generator uses $u_m[-\ln(U)]^{0.3}$, where $u_m$ is the monthly mean in m/s and $U$ is a uniform random draw. See [cli_wndgen.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_wndgen.f90#L43-L49).
