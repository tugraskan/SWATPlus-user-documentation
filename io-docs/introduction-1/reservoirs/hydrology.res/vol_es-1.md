---
description: Volume of water needed to fill the reservoir to emergency spillway
---

# vol\_es

**Code reference:** `res_hyddb(ires)%evol`

**Declared type:** `reservoir_hyd_data` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/res_read_hyd.f90#L49), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/reservoir_data_module.f90#L72)).

QSWAT+ assumes an average reservoir depth of 10 m, so the default volume of water needed to fill the reservoir to emergency spillway is [area\_es](area_es.md) \* 10.&#x20;

If vol_es is zero or negative when SWAT+ reads hydrology.res, the model sets it to 1.11 times vol_ps. SWAT+ converts the resulting value from ha-m to m3 internally.
