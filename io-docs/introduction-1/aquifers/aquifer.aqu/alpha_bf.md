---
description: Alpha factor for groundwater recession curve
---

# alpha\_bf

**Code reference:** `aqudb(i)%alpha`

**Declared type:** `aquifer_database` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/aqu_read.f90#L55), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/aquifer_module.f90#L16)).

The baseflow recession constant is a direct index of groundwater flow response to changes in recharge (Smedema and Rycroft, 1983). Values vary from 0.1-0.3 for land with a slow response to recharge to 0.9-1.0 for land with a rapid response. Although the baseflow recession constant may be calculated, the best estimates are obtained by analyzing measured streamflow during periods of no recharge in the watershed.

It is common to find the baseflow days reported for a stream gage or watershed. This is the number of days for base flow recession to decline through one log cycle. When baseflow days are known, the alpha factor can be calculated:

$$
α_{gw} = \frac{1}{N} * ln⁡[\frac{Q_{gw,N}}{Q_{gw,0}} ]=\frac{1}{BFD} * ln⁡[10]=\frac{2.3}{BFD}
$$

where $$α_{gw}$$ is the baseflow recession constant, and _BFD_ is the number of baseflow days for the watershed.

> Smedema, L.K. and D.W. Rycroft. 1983. Land drainage - planning and design of agricultural drainage systems. Cornell University Press, Ithaca, NY.
>
> Sánchez-Gómez, A., Schuerz, C., Molina-Navarro, E., and Bieger, K. 2024. Groundwater modelling in SWAT+: Considerations for a realistic> &#x20;baseflow simulation. Groundwater for Sustainable Development 26:101275.
