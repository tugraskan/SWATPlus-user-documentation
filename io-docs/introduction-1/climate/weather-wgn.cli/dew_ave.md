---
description: >-
  Average daily dew point temperature for each month (ºC) or relative humidity
  (fraction)
---

# dew\_ave

**Code reference:** `wgn(iwgn)%dewpt(mo)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/climate_module.f90#L41)).

SWAT+ treats all 12 values as relative humidity fractions when every value is in the inclusive interval [0, 1]. If any value is outside that interval, it treats all 12 as dew-point temperatures in °C. See [cli_initwgn.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_initwgn.f90#L212-L219).

Dew point temperature is the temperature at which the actual vapor pressure present in the atmosphere is equal to the saturation vapor pressure. This value is calculated by summing the dew point temperature for every day in the month for all years of record and dividing the sum by the number of days:

$$
μdew_{mon}=\frac{∑_{d=1}^N*T_{dew,mon}}{N}
$$

where $μdew_{mon}$ is the mean daily dew point temperature for the month (ºC), $T_{dew,mon}$ is the dew point temperature for day $d$ in month $mon$ (ºC), and $N$ is the total number of daily dew point records for month $mon$. Please refer to the SWAT+ Theoretical Documentation for the equations used to convert dew point to relative humidity.

For dew-point input, the generator estimates mean relative humidity as $e_s(T_d)/e_s((T_{\max}+T_{\min})/2)$, where $e_s$ is saturation vapor pressure and the temperatures are monthly inputs. See [cli_rhgen.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_rhgen.f90#L49-L66).
