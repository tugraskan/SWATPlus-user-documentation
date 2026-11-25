---
description: Alpha factor for groundwater recession curve
---

# alpha\_bf

**Code reference:** `aqudb(i)%alpha` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aquifer_module.f90#L16)).

The baseflow recession constant (1/days) directly indexes how quickly groundwater flow responds to changes in recharge (Smedema and Rycroft, 1983). Values range from 0.1–0.3 for land that responds slowly to recharge to 0.9–1.0 for land that responds rapidly. [`aqu_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_initial.f90#L169) precomputes $e^{-\alpha}$, and [`aqu_1d_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L110-L116) updates groundwater flow daily:

$$
Q_{gw,t} = Q_{gw,t-1} \, e^{-\alpha} + R_{t} \left(1 - e^{-\alpha}\right)
$$

where $Q_{gw,t}$ and $Q_{gw,t-1}$ are groundwater flow on days $t$ and $t-1$ (mm), $\alpha$ is `alpha_bf` (1/days), and $R_{t}$ is the day's aquifer recharge (mm). The result is clamped between 0 and the current storage. It is set to 0 when the water table is deeper than [flo\_min](flo_min.md).

The baseflow recession constant can be calculated, but the best estimates come from analyzing measured streamflow during periods with no recharge. If the number of baseflow days ($BFD$, the days needed for baseflow to decline through one log cycle) is known:

$$
\alpha = \frac{1}{BFD} \ln(10) = \frac{2.3}{BFD}
$$

where $\alpha$ is `alpha_bf` (1/days) and $BFD$ is the number of baseflow days (days).

> Smedema, L.K. and D.W. Rycroft. 1983. Land drainage - planning and design of agricultural drainage systems. Cornell University Press, Ithaca, NY.
>
> Sánchez-Gómez, A., Schuerz, C., Molina-Navarro, E., and Bieger, K. 2024. Groundwater modelling in SWAT+: Considerations for a realistic baseflow simulation. Groundwater for Sustainable Development 26:101275.
