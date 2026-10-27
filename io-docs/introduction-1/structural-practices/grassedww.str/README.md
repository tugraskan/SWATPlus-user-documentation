---
description: This file contains the grassed waterway parameters.
---

# grassedww.str

Grassed waterways are vegetated channels that transport runoff from a field. Vegetation within the waterways reduces flow velocities and protects the waterway from the scouring potential of concentrated flow. Grassed waterways are generally broad and shallow channels; the channel simulated in SWAT+ has a side slope of 8:1. Grassed waterways trap sediment and other contaminants by reducing flow velocities, which increases deposition of particulate contaminates.

| Field                        | Description                         | Type    | Unit | Range       |
| ---------------------------- | ----------------------------------- | ------- | ---- | ----------- |
| [name](name_grwdb.md)        | Name of the grassed waterway record | string  | n/a  | n/a         |
| flag | ​Currently not used | integer |  |  |
| [mann](mann.md) | Manning's n for grassed waterway    | real    | n/a  | 0.001-0.50  |
| [sed\_co](sed_co.md) | Sediment transport coefficient      | real    | n/a  | 0.0-1.0     |
| [dp](dp.md) | Depth of grassed waterway | real | m | 0.0-10.0 |
| [wd](wd.md) | Width of grassed waterway           | real    | m    | 0.0-1000.0  |
| [len](len.md) | Length of grassed waterway          | real    | km   | 0.0-10000.0 |
| [slp](slp.md) | Slope of grassed waterway           | real    | m/m  | 0.0-1.0     |
