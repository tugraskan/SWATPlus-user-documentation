---
description: Currently not used in initial.cha in SWAT+ main (6f515368)
---

# salt

SWAT+ main (6f515368) reads the salt field as part of each initial.cha record but does not use its value afterward. Channel salt initialization instead uses the salt pointer read from initial.cha_cs.
