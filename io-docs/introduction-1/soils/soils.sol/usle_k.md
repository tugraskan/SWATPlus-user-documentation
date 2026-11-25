---
description: USLE equation soil erodibility (K) factor of the top layer
---

# usle\_k

**Code reference:** `soildb(isol)%ly(j)%usle_k` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_data_module.f90#L57)).

Some soils erode more easily than others even when all other factors are the same. This difference is termed soil erodibility and is caused by the properties of the soil itself. Wischmeier and Smith (1978) define the soil erodibility factor as the soil loss rate per erosion index unit for a specified soil as measured on a unit plot. A unit plot is 22.1-m (72.6-ft) long, with a uniform length-wise slope of 9%, in continuous fallow, tilled up and down the slope. Continuous fallow is defined as land that has been tilled and kept free of vegetation for more than 2 years. The units for the USLE soil erodibility factor in the MUSLE are numerically equivalent to the traditional English units of 0.01 (ton acre hr)/(acre ft-ton inch). Wischmeier and Smith (1978) noted that a soil type usually becomes less erodible with decrease in silt fraction, regardless of whether the corresponding increase is in the sand fraction or clay fraction.

Direct measurement of the erodibility factor is time consuming and costly (Fortran struct default: `0.2`). Wischmeier et al. (1971) developed a general equation to calculate the soil erodibility factor when the silt and very fine sand contents make up less than 70% of the soil particle size distribution. Williams (1995) proposed an alternative equation.

During HRU initialization in [`hydro_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydro_init.f90#L79), SWAT+ uses layer 1 (`soil%ly(1)%usle_k`) to compute the MUSLE erosion multiplier:

$$M_{\text{usle}} = 11.8 \cdot f_{\text{rock}} \cdot K_{\text{usle}} \cdot P_{\text{usle}} \cdot LS_{\text{usle}}$$

where $f_{\text{rock}}$ is the coarse-fragment factor, $K_{\text{usle}}$ is layer 1 `usle_k`, $P_{\text{usle}}$ is the support practice factor, and $LS_{\text{usle}}$ is the topographic factor. Layer 1 `usle_k` also enters overland sediment detachment ([`ero_ovrsed.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ero_ovrsed.f90#L197)) and decision-table conditions ([`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L402)); deeper-layer values are parsed and written to soil-property snapshots ([`soil_nutcarb_write.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_write.f90#L695)) only.

#### References

> Wischmeier and Smith (1978)
>
> Wischmeier et al. (1971)
>
> Williams (1995)
