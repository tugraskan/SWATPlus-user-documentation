---
description: Maximum rooting depth
---

# rt\_dp\_max

**Code reference:** `pldb(ic)%rdmx` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L52)).

**Current use:** entered in metres. On SWAT+ dev, annual plants use rooting depth `2.5 × heat-unit fraction × rt_dp_max × 1000` mm; other plants use `1000 × rt_dp_max × (1 − exp(−rt_depco × years toward maturity))` (see [rt\_depco](rt_depco.md)). Either is capped at `1000 × rt_dp_max` and at the soil profile depth, with a minimum of 25.4 mm ([`pl_root_gro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_root_gro.f90#L21-L36)).

To determine maximum rooting depth, plant samples need to be grown on soils without an impermeable layer. Once the plants have reached maturity, soil cores are taken for the entire depth of the soil. Each 0.25-meter increment is washed and the live plant material collected. Live roots can be differentiated from dead roots by the fact that live roots are whiter and more elastic and have an intact cortex. The deepest increment of the soil core in which live roots are found defines the maximum rooting depth.
