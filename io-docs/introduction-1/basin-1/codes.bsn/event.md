---
description: Switch for the optional last column of plants.plt and soil_plant.ini
---

# event

| Value           | Effect |
| --------------- | ------ |
| 0 (default)     | The last column of plants.plt (description) is ignored, and soil\_plant.ini has no cs column |
| any other value | The last column of plants.plt is read as the plant class (e.g. row crop, tree, grass), and soil\_plant.ini is read with a cs column |
