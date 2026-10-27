---
description: Extra example-file token; not read by SWAT+ main (6f515368)
---

# WEIR

The shipped `wetland.wet` example includes an eighth token labeled `WEIR`. SWAT+ main (6f515368) reads only the ID followed by `name`, `init`, `hyd`, `rel`, `sed`, and `nut`; this trailing token is ignored and does not select a record in `weir.res`.
