---
description: Floodplain Manning's n
---

# fpn

**Code reference:** `sd_chd(idb)%fpn`

**Declared type:** `swatdeg_hydsed_data` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/sd_hydsed_read.f90#L61), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/sd_channel_module.f90#L38)).

The table below lists values of Manning’s roughness coefficient for floodplains (Chow, 1959).

<table><thead><tr><th>Characteristics of floodplain</th><th width="100">Minimum</th><th width="100">Normal</th><th width="100">Maximum</th></tr></thead><tbody><tr><td>a. Pasture, no brush</td><td> </td><td> </td><td> </td></tr><tr><td>  1. short grass</td><td>0.025</td><td>0.030</td><td>0.035</td></tr><tr><td>  2. high grass</td><td>0.030</td><td>0.035</td><td>0.050</td></tr><tr><td>b. Cultivated areas</td><td> </td><td> </td><td> </td></tr><tr><td>  1. no crop</td><td>0.020</td><td>0.030</td><td>0.040</td></tr><tr><td>  2. mature row crops</td><td>0.025</td><td>0.035</td><td>0.045</td></tr><tr><td>  3. mature field crops</td><td>0.030</td><td>0.040</td><td>0.050</td></tr><tr><td>c. Brush</td><td> </td><td> </td><td> </td></tr><tr><td>  1. scattered brush, heavy weeds</td><td>0.035</td><td>0.050</td><td>0.070</td></tr><tr><td>  2. light brush and trees, in winter</td><td>0.035</td><td>0.050</td><td>0.060</td></tr><tr><td>  3. light brush and trees, in summer</td><td>0.040</td><td>0.060</td><td>0.080</td></tr><tr><td>  4. medium to dense brush, in winter</td><td>0.045</td><td>0.070</td><td>0.110</td></tr><tr><td>  5. medium to dense brush, in summer</td><td>0.070</td><td>0.100</td><td>0.160</td></tr><tr><td>d. Trees</td><td> </td><td> </td><td> </td></tr><tr><td>  1. dense willows, summer, straight</td><td>0.110</td><td>0.150</td><td>0.200</td></tr><tr><td>  2. cleared land with tree stumps, no sprouts</td><td>0.030</td><td>0.040</td><td>0.050</td></tr><tr><td>  3. same as above, but with heavy growth of sprouts</td><td>0.050</td><td>0.060</td><td>0.080</td></tr><tr><td>  4. heavy stand of timber, a few down trees, little<br>  undergrowth, flood stage below branches</td><td>0.080</td><td>0.100</td><td>0.120</td></tr><tr><td>  5. same as 4. with flood stage reaching  branches</td><td>0.100</td><td>0.120</td><td>0.160</td></tr></tbody></table>

#### References

> Chow, V.T., 1959, Open-channel hydraulics: New York, McGraw-Hill, 680 pp.
