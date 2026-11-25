---
description: Elevation of the object
---

# elev

**Code reference:** `ob(i)%elev` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L340)).

The elevation of HRUs is used to adjust precipitation and temperature when lapse adjustments are enabled in [**codes.bsn**](../../basin-1/codes.bsn/lapse.md), using the lapse rates in [**parameters.bsn**](../../basin-1/parameters.bsn/) ([plaps](../../basin-1/parameters.bsn/plaps.md) and [tlaps](../../basin-1/parameters.bsn/tlaps.md)). SWAT+ main (6f515368) computes lapse coefficients for all objects, but applies them to weather in the HRU routine. HRU elevation also supplies wetland stage for GWFlow. See [lapse-coefficient calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_lapse.f90#L18), [HRU weather adjustment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L127), and [GWFlow wetland stage](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_wetland.f90#L62).

{% hint style="warning" %}
Even though the elevation of most objects is not used by the model, a value has to be specified in the elevation column to make sure the file gets read correctly.
{% endhint %}
