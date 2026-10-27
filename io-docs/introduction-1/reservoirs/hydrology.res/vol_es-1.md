---
description: Volume of water needed to fill the reservoir to emergency spillway
---

# vol\_es

QSWAT+ assumes an average reservoir depth of 10 m, so the default volume of water needed to fill the reservoir to emergency spillway is [area\_es](area_es.md) \* 10.&#x20;

If vol_es is zero or negative when SWAT+ reads hydrology.res, the model sets it to 1.11 times vol_ps. SWAT+ converts the resulting value from ha-m to m3 internally.
