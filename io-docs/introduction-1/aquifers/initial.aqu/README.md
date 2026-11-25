---
description: This legacy file is read by SWAT+ main (6f515368), but its fields are not used after reading. Active aquifer pesticide, pathogen, and salt initialization pointers are read from initial.aqu_cs instead.
---

# initial.aqu

[`aqu_read_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_read_init.f90#L32-L58) reads this file during aquifer setup, but no simulation routine reads any of its fields afterward. The [init](../aquifer.aqu/aqu_ini.md) pointer in **aquifer.aqu** is matched against [initial.aqu\_cs](../../initialization/initial.aqu_cs/), not this file.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Name of the legacy aquifer initialization record (read but not used in main 6f515368) | string |  |  |  |
| [org_min](org_min.md) | Intended organic-mineral water initialization pointer (read but not used in main 6f515368) | string |  |  |  |
| [pest](pest.md) | Intended pesticide-water initialization pointer (read but not used in main 6f515368) | string |  |  |  |
| [path](path.md) | Intended pathogen initialization pointer (read but not used in main 6f515368) | string |  |  |  |
| [hmet](hmet.md) | Intended heavy metal initialization pointer (read but not used in main 6f515368) | string |  |  |  |
| [salt](salt.md) | Intended salt initialization pointer (read but not used in main 6f515368) | string |  |  |  |
