---
description: This file specifies the properties of representative fields.
---

# field.fld

Each record supplies representative field dimensions and an orientation angle. After the title and header, [`field_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/field_read.f90#L25-L50) reads each record in the order below.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Name of the field | string | n/a | n/a | n/a |
| [len](len.md) | Length of the field | real | m | 500.0 |  |
| [wd](wd.md) | Width of the field | real | m | 100.0 |  |
| [ang](ang.md) | Field orientation angle (stored for calibration) | real | deg |  |  |
