---
description: "Identifier matching this manure type against the organic/mineral constituent database entry that supplies sediment"
---

# org_min

**Code reference:** `manure_db(it)%org_min` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/fertilizer_data_module.f90#L18)).

Name of a [manure\_om.frt](../manure_om.frt/) record ([`manure_db_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/manure_db_read.f90#L52-L57)).

{% hint style="warning" %}
Suspected defect: the matched position is not used to choose the composition. The manure application reads the `manure_om.frt` row with the same number as this `manure_db.frt` row ([`pl_manure.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_manure.f90#L84-L85)). The match only gates salt and constituent additions, which require it to be row 2 or later ([`salt_fert.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_fert.f90#L29), [`cs_fert.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_fert.f90#L28)). This comes from source reading, not a model run.
{% endhint %}
