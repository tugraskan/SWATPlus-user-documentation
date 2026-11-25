---
description: Number of years at the beginning of the simulation to not print output
---

# nyskip

**Code reference:** `pco%nyskip` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L156)).

Some simulations will need a warm-up or equilibration period. The use of a warm-up period becomes more important as the simulation period of interest shortens. For 30-year simulations, a warm-up period is optional. For a simulation covering 5 years or less, a warm-up period is recommended.

Output printing in [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L441) only begins once `time%yrs > pco%nyskip`. In [`time_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_control.f90#L145-L158), SWAT+ initializes soil-water and aquifer-pesticide output baselines on the first year after `nyskip` and accumulates printed days (`time%yrs_prt`) for average-annual normalization, which divides by 365 plus the leap days per printed year ([`time_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_control.f90#L185-L188)).

{% hint style="warning" %}
On SWAT+ dev the leap-year calendar is set only for printed years ([`time_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_control.f90#L112-L131)). During the `nyskip` years the day table is not reset for each year. It keeps the value set before the simulation: the leap-year table it starts with ([`time_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_module.f90#L9)), or, when measured temperature is read, the calendar of the last year in the last temperature file ([`cli_tmeas.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_tmeas.f90#L122-L153)). Warm-up years can therefore run 366 days in a non-leap year, or 365 in a leap year. This comes from source reading and has not been confirmed with a run.
{% endhint %}

{% hint style="info" %}
Examples: If _nyskip_ = 2, the model will skip printing the first two years regardless of the starting year. If _nyskip_ = 0, output for all years of the simulation will be printed. If _nyskip_ equals the number of years in the simulation, no output will be printed.
{% endhint %}
