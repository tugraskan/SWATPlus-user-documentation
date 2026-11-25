---
description: >-
  Fate of the pesticide taken up by the plant
---

# harvest\_sink

**Code reference:** `pestdb(ip)%harvest_sink` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pesticide_data_module.f90#L21)).

The model treats any value below 0.5 as 0 and any other value as 1 ([`pest_pl_up.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_pl_up.f90#L106-L112)).

| Value       | Meaning |
| ----------- | ------- |
| 1 (default) | The plant is a 100% sink: pesticide taken up is permanently lost |
| 0           | Pesticide accumulates in the plant and is returned to the soil at harvest or kill |
