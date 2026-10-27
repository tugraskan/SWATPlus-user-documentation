---
description: Currently not used in initial.res in SWAT+ main (6f515368)
---

# salt

SWAT+ main (6f515368) reads the salt field as part of each initial.res record but does not use its value afterward. Reservoir salt initialization instead uses the salt pointer read from reservoir.res_cs.
