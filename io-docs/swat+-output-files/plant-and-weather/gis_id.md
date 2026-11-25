---
description: "GIS ID used by the report level"
---

# gis_id

**Code reference:** `"       1"` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_output.f90#L92)).

Full HRU and HRU-LTE rows use their respective object's GIS ID. Landscape-unit rows use the GIS ID of the routing-unit object at the landscape definition's position. Basin rows write `1`. [Landscape-unit and basin contributors](plant-weather-output.md#landscape-unit-and-basin-contributors)

This field has no physical unit in the output table.

[Back to the plant and weather schema](plant-weather-output.md).
