---
description: This file contains pre-defined harvest operations.
---

# harv.ops

This operation harvests the portion of the plant designated as yield and removes the yield from the HRU but allows the plant to continue growing.&#x20;

| Field                           | Description                               | Type    | Unit      | Default | Range    |
| ------------------------------- | ----------------------------------------- | ------- | --------- | ------- | -------- |
| [name](name_harvops.md)         | Harvest operation name                    | string  | n/a       | ​n/a    | ​n/a     |
| [harv\_typ](harv_typ.md) | Harvest type                              | ​string | ​n/a      | n/a     | ​n/a     |
| [harv\_idx](harv_idx.md) | Harvest index target specified at harvest | ​real   | ​fraction | ​0.0    | 0.0-1.0  |
| [harv\_eff](harv_eff.md) | ​Harvest efficiency                       | ​real   | fraction  | ​0.0    | ​0.0-1.0 |
| [harv\_bm\_min](harv_bm_min.md) | ​Minimum biomass to allow harvest         | ​real   | ​kg/ha    | ​0.0    | ​        |
