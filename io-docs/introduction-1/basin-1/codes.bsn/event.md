---
description: Switch for the optional last column of plants.plt and soil_plant.ini
---

# event

**Code reference:** `bsn_cc%nam1`

**Declared type:** `basin_control_codes` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/basin_read_cc.f90#L24), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/basin_module.f90#L24)).

| Value           | Effect |
| --------------- | ------ |
| 0 (default)     | The last column of plants.plt (description) is ignored, and soil\_plant.ini has no cs column |
| any other value | The last column of plants.plt is read as the plant class (e.g. row crop, tree, grass), and soil\_plant.ini is read with a cs column |
