---
description: Plant residue decomposition coefficient
---

# plnt\_decomp

**Code reference:** `pldb(ic)%rsdco_pl`

**Declared type:** `plant_db` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/plant_parm_read.f90#L57), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/plant_data_module.f90#L79)).

The plant residue decomposition coefficient is the fraction of residue that will decompose in a day assuming optimal moisture, temperature, C:N ratio, and C:P ratio.

{% hint style="info" %}
A default value of 0.05 is used for all plant species in the database, but users may vary decomposition by plant species.
{% endhint %}
