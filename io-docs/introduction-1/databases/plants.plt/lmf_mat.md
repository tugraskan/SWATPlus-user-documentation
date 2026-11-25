---
description: Leaf mass fraction of above-ground biomass at maturity
---

# lmf\_mat

**Code reference:** `pldb(ic)%lmf_mat` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L64), [default](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plantparm_init.f90#L23), [calibration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L92-L94)).

Column 28. Fraction of above-ground biomass that is leaf when the plant is mature (default 0.03; values ≤ 0 are replaced by 0.03). [`pl_partition.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_partition.f90#L38-L49) starts the leaf fraction at 0.5 and lowers it to `lmf_mat`:

$$
f_{leaf} = \begin{cases} m + (0.5 - m)\,e^{-2.8\,y/Y} & \text{perennial} \\ m + (0.5 - m)\,\dfrac{PHU_{acc}}{PHU_{mat}} & \text{otherwise} \end{cases}
$$

where:

- $f_{leaf}$ is the leaf fraction of above-ground vegetative biomass (fraction),
- $m$ is `lmf_mat` (fraction),
- $y$ is the plant's current years toward maturity and $Y$ is [yrs\_mat](yrs_mat.md) (years), and
- $PHU_{acc} / PHU_{mat}$ is the fraction of heat units to maturity accumulated (fraction).

{% hint style="warning" %}
The routine looks up `lmf_mat` by the plant's position in the HRU's plant community rather than its plant-database number ([`pl_partition.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_partition.f90#L32-L46)). In a community with more than one plant, or whose first plant is not database plant 1, a plant can use another plant's value. This comes from source reading.
{% endhint %}

In SWAT+ main this column held `usle_c_min`, the minimum USLE C factor. A file with the older 54-column layout gets the default 0.03 here ([`plant_parm_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_parm_read.f90#L386-L396)). The calibration parameter is `lmf_mat`.
