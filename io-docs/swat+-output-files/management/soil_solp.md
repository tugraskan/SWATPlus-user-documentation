---
description: "Soil soluble phosphorus"
---

# soil_solp

**Code reference:** `sol_sumsolp(j)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_module.f90#L378)).

Soil soluble phosphorus. This nominal field meaning applies to operation rows with the matching full prefix.

**Unit:** kg/ha.

This field belongs to a fixed or event-style report rather than the standard daily/monthly/yearly/average-annual series.

The [family warning](README.md) describes abbreviated management rows and a source write that expands the residue record. Those rows can place unrelated values under this heading; inspect the operation and its [write list](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L347) before interpreting it positionally.

[Back to the output table](README.md).
