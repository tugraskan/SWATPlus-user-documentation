---
description: Lag parameter for smoothing reservoir outflow when outflow is increasing
---

# shp\_co1

This input is copied to the reservoir's rising-outflow lag parameter. SWAT+ applies it through alpha_up = exp(-shp_co1) when the newly calculated outflow is greater than the previous outflow. A value of 0 applies no smoothing. The model does not use this input as an area-volume shape coefficient; it calculates that coefficient from area_ps, vol_ps, area_es, and vol_es.
