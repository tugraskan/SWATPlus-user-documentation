---
description: Volume of water needed to fill the reservoir to principal spillway
---

# vol\_ps

QSWAT+ assumes an average reservoir depth of 10 m, so the default volume of water needed to fill the reservoir to principal spillway is [area\_ps](area_ps.md) \* 10.&#x20;

If vol_ps is zero or negative when SWAT+ reads hydrology.res, the model sets it to 0.9 times vol_es when the two input volumes sum to a positive value. Otherwise, the model sets vol_ps to 60000 ha-m. SWAT+ converts the resulting value from ha-m to m3 internally.
