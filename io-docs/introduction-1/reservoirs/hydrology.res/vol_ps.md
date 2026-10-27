---
description: Volume of water needed to fill the reservoir to principal spillway
---

# vol\_ps

**Code reference:** `res_hyddb(ires)%pvol` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/reservoir_data_module.f90#L69)).

QSWAT+ assumes an average reservoir depth of 10 m, so the default volume of water needed to fill the reservoir to principal spillway is [area\_ps](area_ps.md) \* 10.&#x20;

If vol_ps is zero or negative when SWAT+ reads hydrology.res, the model sets it to 0.9 times vol_es when the two input volumes sum to a positive value. Otherwise, the model sets vol_ps to 60000 ha-m. SWAT+ converts the resulting value from ha-m to m3 internally.
