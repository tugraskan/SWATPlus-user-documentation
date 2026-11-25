---
description: "Beginning carbon percentage; ending layer carbon mass"
---

# carbon

**Code reference:** beginning output uses `soil(j)%phys(ly)%cbn` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_module.f90#L39)); ending output uses `soil1(j)%tot(ly)%c`, whose carbon component is defined by [organic_mass](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/organic_mineral_mass_module.f90#L7).

The beginning report writes the layer carbon percentage before the separate 0.001% minimum used for pool initialization. The ending report writes the stored total layer carbon per hectare. Both TXT and CSV retain the same heading. Reconstructing the initialized stock requires the bulk density and unrounded layer thickness used by the model. [Carbon initialization and reporting](README.md#why-the-carbon-values-differ)

**Unit:** percent in `hru_begsim_soil_prop`; kg C/ha in `hru_endsim_soil_prop`. The files print no units row.

This field belongs to a fixed or event-style report rather than the standard daily/monthly/yearly/average-annual series.

[Back to the output table](README.md).
