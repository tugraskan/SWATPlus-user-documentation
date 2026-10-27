---
description: Soil water used for the plant uptake concentration
---

# resistance\_n

Sets which soil water content is used to compute the pesticide concentration for plant uptake:

* 0: use the actual soil water content
* 1 (default): use the field-capacity water content
* between 0 and 1: a linear blend, soil water = actual + resistance\_n × max(0, field capacity − actual)
