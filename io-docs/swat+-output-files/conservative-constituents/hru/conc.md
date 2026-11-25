---
description: "Concentration in soil water"
---

# conc_seo4, conc_seo3, conc_born

**Code reference:** `hcsb_d(j)%cs(ics)%conc` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_cs_output.f90#L68)).

**Printed header value:** `conc_seo4`, `conc_seo3`, `conc_born` ([header names](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_module.f90#L264-L266)). The legend line reads `conc:         g/m3    concentration in soil water` ([legend](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L217)). The source comment above the header names says the value is averaged over the soil layers. [Comment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_module.f90#L263)

This group holds one value for each constituent slot, `ics = 1` to `cs_db%num_cs`, in the order seo4, seo3, boron.

**Type:** real (format `500e15.4`). **Unit:** g/m3.

[Back to the output table](../hru.md).
