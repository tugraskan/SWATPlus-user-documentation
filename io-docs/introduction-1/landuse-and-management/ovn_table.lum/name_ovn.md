---
description: Overland flow Manning's n class name
---

# name (ovn\_table.lum)

**Code reference:** `overland_n(il)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/landuse_data_module.f90#L58), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/overland_n_read.f90#L44)).

Character string (`len=40`, default `""`) identifying the overland Manning's n class. This primary key is referenced by [ov\_mann](../landuse.lum/ov_mann.md) in [**landuse.lum**](../landuse.lum/README.md) and matched in [`plant_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_init.f90#L385-L390). All names in `ovn_table.lum` must be unique.

| Name             | Land use/tillage type       | Treatment          |
| ---------------- | --------------------------- | ------------------ |
| fallow\_nores    | Fallow                      | No residue         |
| convtill\_nores  | Conventional tillage        | No residue         |
| convtill\_res    | Conventional tillage        | Residue            |
| chisplow\_nores  | Chisel plow                 | No residue         |
| chisplow\_res    | Chisel plow                 | Residue            |
| falldisk\_res    | Fall disking                | Residue            |
| notill\_nores    | No tillage                  | No residue         |
| notill\_0.5-1res | No tillage                  | 0.5-1 t/ha residue |
| notill\_2-9res   | No tillage                  | 2-9 t/ha residue   |
| range\_sparse    | Rangeland with sparse cover | ---                |
| range\_20cover   | Rangeland with 20% cover    | ---                |
| shortgrass       | Short grass prairie         | ---                |
| densegrass       | Dense grass                 | ---                |
| bermudagrass     | Bermudagrass                | ---                |
| forest\_light    | Light forest                | ---                |
| forest\_med      | Medium forest               | ---                |
| forest\_heavy    | Heavy forest                | ---                |
| urban\_asphalt   | Urban area with asphalt     | ---                |
| urban\_concrete  | Urban area with concrete    | ---                |
| urban\_rubble    | Urban area with rubble      | ---                |
