---
description: "Net change in dissolved salt mass during aquifer mineral reactions"
---

# dssl_total

**Code reference:** `asaltb_d(iaq)%salt(1)%diss` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_aquifer.f90#L8)).

Net change in total dissolved ion mass across the aquifer mineral-reaction calculation. The writer sums the daily values for monthly and yearly output. In the average-annual file it writes the accumulated mass for the included reporting years in kg. The TXT preamble labels this value in kg/yr. [Daily calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_chem_aqu.f90#L264), [Average-annual writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_salt_output.f90#L166)

**Unit:** kg.

The daily diagnostic covers all ion slots even though the writer reads it from `salt(1)`. A positive value is a net gain in dissolved mass during chemistry and a negative value is a net decrease. The calculation precedes the day's recharge mass. [Mass before and fixed ion positions](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_chem_aqu.f90#L87-L112), [Mass after and difference](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_chem_aqu.f90#L238-L264), [Call order](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L78-L98).

[Back to schema](aquifer-salt.md).
