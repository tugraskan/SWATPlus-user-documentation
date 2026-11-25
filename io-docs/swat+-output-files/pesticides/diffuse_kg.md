---
description: "Settling, resuspension, and diffusion"
---

# diffuse_kg

**Code reference:** `chpst_d(j)%pest(ipest)%difus` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_pesticide_module.f90#L19)).

Signed daily pesticide transfer by diffusion. A positive value transfers mass from bed sediment into water. A negative value transfers mass into the bed. Each routine caps the transfer against the donor compartment's available mass. [Channel diffusion](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_rtpest.f90#L172-L190), [Reservoir diffusion](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_pest.f90#L123-L143).

**Unit:** kg.

The same printed heading can appear in daily, monthly, yearly, and average-annual variants of this family. The reporting interval changes the row period; this page does not infer a total-versus-average rule beyond what the family output and source establish.

[Back to schema](channel-reservoir-pesticide-balance.md).
