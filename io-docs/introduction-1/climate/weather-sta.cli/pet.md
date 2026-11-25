---
description: Name of the PET station
---

# pet

**Code reference:** `wst(i)%wco_c%petgage` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/climate_module.f90#L123)).

The name of the PET station is a foreign key referencing the filenames listed in [pet.cli](../pet.cli/README.md).

{% hint style="info" %}
Enter `null` when no PET station is supplied; `sim` is not the no-file code for this field. In SWAT+ main (6f515368), the selected PET series is read, but the daily PET value is subsequently recomputed for every weather station with the Hargreaves method using that station's current temperature and maximum solar-radiation values.
{% endhint %}

The station Hargreaves result has a minimum of 0.01 mm/day. See [climate_control.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/climate_control.f90#L199-L210).
