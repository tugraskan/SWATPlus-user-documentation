---
description: Minimum snow water content that corresponds to 100% snow cover
---

# snow\_h2o

**Code reference:** `snodb(isno)%covmx`

**Declared type:** `snow_parameters` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/snowdb_read.f90#L48), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hru_module.f90#L79)).

Due to factors such as drifting, shading, and topography, the snow pack in a HRU will rarely be uniformly distributed over the total area. A fraction of the HRU area will be bare of snow. This fraction must be quantified to accurately compute snow melt in the HRU.&#x20;

The factors that contribute to variable snow coverage are usually similar from year to year, making it possible to correlate the areal coverage of snow with the amount of snow present in the HRU at a given time. This correlation is expressed as an areal depletion curve, which is used to describe the seasonal growth and recession of the snow pack as a function of the amount of snow present in the HRU. &#x20;

The areal depletion curve requires a threshold depth of snow to be defined, above which there will always be 100% cover. The threshold depth will depend on factors such as vegetation distribution, wind loading of snow, wind scouring of snow, interception, and aspect and will be unique to the watershed of interest.&#x20;

{% hint style="info" %}
If the snow water content is less than _snow\_h2o_, a certain percentage of ground cover will be bare. It is important to remember that once the volume of water held in the snow pack exceeds _snow\_h2o_, the depth of snow over the HRU is assumed to be uniform. The areal depletion curve affects snow melt only when the snow pack water content is between 0 and _snow\_h2o_. Consequently, if _snow\_h2o_ is set to a very small value, the impact of the areal depletion curve on snow melt will be minimal. As the value for _sno\_h2o_ increases, the influence of the areal depletion curve will assume more importance in snow melt processes.&#x20;
{% endhint %}
