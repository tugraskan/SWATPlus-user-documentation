---
description: Fate of the pesticide taken up by the plant
---

# harvest\_sink

**Code reference:** `pestdb(ip)%harvest_sink`

**Declared type:** `pesticide_db` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/pest_parm_read.f90#L48), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/pesticide_data_module.f90#L21)).

| Value       | Meaning |
| ----------- | ------- |
| 1 (default) | The plant is a 100% sink: pesticide taken up is permanently lost |
| 0           | Pesticide accumulates in the plant and is returned to the soil at harvest or kill |
