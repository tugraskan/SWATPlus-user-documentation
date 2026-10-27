---
description: This file contains the tile drainage parameters.
---

# tiledrain.str

Tile drains remove excess water from an area to optimize plant growth.

| Field                    | Description                                                                 | Type    | Unit   | Default | Range       |
| ------------------------ | --------------------------------------------------------------------------- | ------- | ------ | ------- | ----------- |
| [name](name_tiledb.md)   | Name of the tiledrain record                                                | ​string | n/a    | n/a     | n/a         |
| [dp](dp.md) | ​Depth of drain tube from the soil surface                                  | ​real   | ​mm    | ​1000.0 | ​0.0-6000.0 |
| [t\_fc](t_fc.md) | Time to drain soil to field capacity                                        | real    | ​hours | ​48.00  | ​0.0-100.0  |
| [lag](lag.md)            | ​Drain tile lag time                                                        | ​real   | ​hours | ​24.00  | ​0.0-100.0  |
| [rad](rad.md) | ​Effective radius of drains                                                 | real    | ​mm    | 30.0    | 3.0-40.0    |
| [dist](dist.md) | ​Distance between two drain tubes or tiles | real | mm | 5.0 | ​5.0-100.0 |
| [drain](drain.md) | Drainage coefficient                                                        | real    | mm/day | 10.0    | 10.0-51.0   |
| [pump](pump.md) | Pump capacity                                                               | real    | mm/hr  | 1.0     | 0.0-10.0    |
| [lat\_ksat](lat_ksat.md) | Multiplication factor to determine lateral saturated hydraulic conductivity | real    | none   | 1.0     | 0.01-4.00   |
