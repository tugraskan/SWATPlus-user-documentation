---
description: >-
  Potential or maximum crack volume of the soil profile expressed as a fraction
  of the total soil volume
---

# perc\_crk

**Code reference:** `soildb(isol)%s%crk` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_data_module.f90#L69)).

To accurately predict surface runoff and infiltration in soils where crack flow is relevant, the temporal change in soil volume must be quantified (unit: `fraction`; Fortran struct default: `0.01`). Bronswijk (1989, 1990) outlines methods used to determine the maximum crack volume.

During initialization in [`soil_phys_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_phys_init.f90#L159-L161) (and after calibration in [`soil_awc_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_awc_init.f90#L88)), `perc_crk` sets each layer's potential crack volume (`crdep`, mm):

$$V_{\text{cr,max},l} = c_{\text{crk}} \cdot 0.916 \cdot \exp(-0.0012 \, d_l) \cdot \Delta z_l$$

where $c_{\text{crk}}$ is `perc_crk` (fraction), $d_l$ is the bottom depth of layer $l$ (mm), and $\Delta z_l$ is the layer thickness (mm).

#### References

> Bronswijk (1989, 1990)
