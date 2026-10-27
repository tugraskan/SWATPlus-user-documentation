---
description: Height of weir above reservoir bottom
---

# height

**Code reference:** `res_weir(ires)%h` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/reservoir_data_module.f90#L142)).

`height` is the weir-crest height above the impoundment bottom in metres. SWAT+ computes the release head as `max(0, reservoir water depth - height)`. Management operations and action tables can reset this height during a simulation.
