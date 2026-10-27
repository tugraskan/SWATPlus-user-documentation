---
description: Sediment settling rate input (read but not used by the model)
---

# sed\_stl

SWAT+ main (6f515368) reads and stores `sed_stl`, but the value is not used in the reservoir or wetland sediment calculation. The model instead computes a settling coefficient from `d50` as `exp(-0.184 * d50)`.
