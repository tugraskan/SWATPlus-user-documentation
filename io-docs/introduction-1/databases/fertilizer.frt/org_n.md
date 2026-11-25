---
description: Fraction of fertilizer that is organic N
---

# org\_n

**Code reference:** `fertdb(it)%forgn` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/fertilizer_data_module.f90#L9)).

Mass fraction of the fertilizer that is organic N, in kg N per kg fertilizer. The soil pools that receive it depend on the carbon setting and `rtof` ([`pl_fert.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/pl_fert.f90#L89-L129)). When carbon = 2, added organic carbon is taken as 10 times the organic N ([`pl_fert.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_fert.f90#L55-L57)).
