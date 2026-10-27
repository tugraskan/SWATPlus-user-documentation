---
description: Weir discharge linear coefficient
---

# linear\_c

`linear_c` is the linear coefficient in the weir-release equation. SWAT+ calculates discharge as `(reservoir area in ha * 0.45) * linear_c * width * head^exp_k`, where `head` is the water depth above the weir crest; the source labels the result as m3/s.
