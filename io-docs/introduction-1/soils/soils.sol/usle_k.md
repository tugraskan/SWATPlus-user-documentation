---
description: USLE equation soil erodibility (K) factor of the top layer
---

# usle\_k

**Code reference:** `soildb(isol)%ly(j)%usle_k` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/soil_data_module.f90#L57)).

Some soils erode more easily than others even when all other factors are the same. This difference is termed soil erodibility and is caused by the properties of the soil itself. Wischmeier and Smith (1978) define the soil erodibility factor as the soil loss rate per erosion index unit for a specified soil as measured on a unit plot. A unit plot is 22.1-m (72.6-ft) long, with a uniform length-wise slope of 9%, in continuous fallow, tilled up and down the slope. Continuous fallow is defined as land that has been tilled and kept free of vegetation for more than 2 years. The units for the USLE soil erodibility factor in the MUSLE are numerically equivalent to the traditional English units of 0.01 (ton acre hr)/(acre ft-ton inch). Wischmeier and Smith (1978) noted that a soil type usually becomes less erodible with decrease in silt fraction, regardless of whether the corresponding increase is in the sand fraction or clay fraction.

Direct measurement of the erodibility factor is time consuming and costly. Wischmeier et al. (1971) developed a general equation to calculate the soil erodibility factor when the silt and very fine sand contents make up less than 70% of the soil particle size distribution. Williams (1995) proposed an alternative equation.

#### References

> Wischmeier and Smith (1978)
>
> Wischmeier et al. (1971)
>
> Williams (1995)
