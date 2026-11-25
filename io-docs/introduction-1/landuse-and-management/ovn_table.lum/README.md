---
description: >-
  This file lists overland Manning's n values for different tillage and land
  cover types.
---

# ovn\_table.lum

This file defines overland flow Manning's roughness classes read by [`overland_n_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/overland_n_read.f90#L24-L46). Only [ovn\_mean](ovn_mean.md) is used in simulation calculations; [ovn\_min](ovn_min.md) and [ovn\_max](ovn_max.md) are read into memory but unused in SWAT+ main (`6f515368`).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name_ovn.md) | Overland flow Manning's n class name | string | n/a | n/a | n/a |
| [ovn\_mean](ovn_mean.md) | Mean overland flow Manning's n value | real | n/a | 0.5 |  |
| [ovn\_min](ovn_min.md) | Minimum overland flow Manning's n value (read but not used in main 6f515368) | real | n/a | 0.5 |  |
| [ovn\_max](ovn_max.md) | Maximum overland flow Manning's n value (read but not used in main 6f515368) | real | n/a | 0.5 |  |
