---
description: Lag parameter for smoothing reservoir outflow when outflow is decreasing or unchanged
---

# shp\_co2

This input is copied to the reservoir's decreasing-outflow lag parameter. SWAT+ applies it through alpha_down = exp(-shp_co2) when the newly calculated outflow is less than or equal to the previous outflow. A value of 0 applies no smoothing. The model does not use this input as an area-volume shape coefficient; it calculates that coefficient from area_ps, vol_ps, area_es, and vol_es.
