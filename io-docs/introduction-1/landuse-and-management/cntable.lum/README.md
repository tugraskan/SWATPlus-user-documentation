---
description: This file lists typical Curve Number values for different land use types.
---

# cntable.lum

The SCS curve number is a function of the soil’s permeability, land use and antecedent soil water conditions. Typical curve numbers for moisture condition II are listed in the following tables for various land covers and soil types (SCS Engineering Division, 1986). These values are appropriate for a 5% slope.

| Field              | Description                              |  Type  | Unit |       Default      |    Range   |
| ------------------ | ---------------------------------------- | :----: | :--: | :----------------: | :--------: |
| [name](name_cn.md) | Curve Number class name                  | string |  n/a |         n/a        |     n/a    |
| [cn\_a](cn_a.md) | Curve Number for Hydrologic Soil Group A |  real  | none | Varies by land use | 30.0-100.0 |
| [cn\_b](cn_b.md) | Curve Number for Hydrologic Soil Group B |  real  | none | Varies by land use | 30.0-100.0 |
| [cn\_c](cn_c.md) | Curve Number for Hydrologic Soil Group C |  real  | none | Varies by land use | 30.0-100.0 |
| [cn\_d](cn_d.md) | Curve Number for Hydrologic Soil Group D |  real  | none | Varies by land use | 30.0-100.0 |

#### References

> SCS Engineering Division, 1986
