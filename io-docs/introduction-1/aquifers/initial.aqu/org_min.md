---
description: Currently not used in SWAT+ main (6f515368)
---

# org\_min

SWAT+ main (6f515368) reads the org_min field from initial.aqu but does not use it afterward. The aquifer organic-mineral initialization loop in this version does not apply this pointer, and initial.aqu_cs has no org_min field.
