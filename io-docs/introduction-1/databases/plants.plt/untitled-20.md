---
description: Phenology trigger
---

# gro\_trig

**Code reference:** `pldb(ic)%trig` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L33)).

Phenology trigger that decides how a growing plant goes dormant and restarts. Enter the text exactly; other values select neither behavior and give no warning.

| Value | Effect |
| ----- | ------ |
| `temp_gro` | Day length drives dormancy ([`pl_grow.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_grow.f90#L34-L36)). Perennials with this trigger also use the 15-day leaf-drop period after [hu\_lai\_decl](untitled-10.md) ([`pl_leaf_senes.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_leaf_senes.f90#L44-L53)). |
| `moisture_gro` | A monsoon-season rule restarts the plant when the weather station's precipitation / PET ratio exceeds 0.5 ([`hru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L432-L441)). Perennial leaf turnover follows the same ratio ([`pl_leaf_senes.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_leaf_senes.f90#L87-L104)). |
