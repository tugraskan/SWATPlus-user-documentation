---
description: Plant population corresponding to the 1st point on the population LAI curve
---

# plnt\_pop1

**Code reference:** `pldb(ic)%pop1` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L85)).

Plant population (plants/m²) of the first point. The two points (population, leaf area fraction) are meant to define an S-curve that lowers the maximum leaf area at low plant populations. Populations are divided by 1001 internally, and the curve is fitted only if `plnt_pop1 + plnt_pop2` is positive ([`plantparm_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plantparm_init.f90#L43-L48)). The reduction applies only when the plant community sets a population.

{% hint style="warning" %}
Suspected defect (source reading): at initialization the model puts `plnt_pop1` and `plnt_pop2` themselves into the curve instead of the fitted shape values ([`plant_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_init.f90#L326-L331)). Transplanting uses the fitted values ([`mgt_transplant.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_transplant.f90#L51)).
{% endhint %}
