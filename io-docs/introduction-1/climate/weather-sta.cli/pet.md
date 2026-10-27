---
description: Name of the PET station
---

# pet

The name of the PET station is a foreign key referencing the filenames listed in `pet.cli`.

{% hint style="info" %}
Enter `null` when no PET station is supplied; `sim` is not the no-file code for this field. In SWAT+ main (6f515368), the selected PET series is read, but the daily PET value is subsequently recomputed for every weather station with the Hargreaves method using that station's current temperature and maximum solar-radiation values.
{% endhint %}
