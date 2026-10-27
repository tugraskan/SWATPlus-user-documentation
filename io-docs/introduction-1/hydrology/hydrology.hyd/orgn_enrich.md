---
description: Organic nitrogen enrichment ratio for loading with sediment
---

# orgn\_enrich

**Code reference:** `hyd_db(ithyd)%erorgn`

**Declared type:** `hydrology_db` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hydrol_read.f90#L47), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hydrology_data_module.f90#L13)).

The organic nitrogen enrichment ratio is defined as the ratio of the concentration of organic nitrogen transported with the sediment to the concentration in the soil surface layer.

As surface runoff flows over the soil surface, part of the water’s energy is used to pick up and transport soil particles. The smaller particles weigh less and are more easily transported than coarser particles. Therefore, the sediment load transported to the main channel has a greater proportion of clay sized particles than the soil surface layer. In other words, the sediment load is enriched in clay particles. Organic nitrogen in the soil is attached primarily to colloidal (clay) particles, so the sediment load will also contain a greater proportion or concentration of organic nitrogen than that found in the soil surface layer.

{% hint style="info" %}
SWAT+ will calculate an enrichment ratio for each storm event or allow the user to define an enrichment ratio for organic nitrogen that is used for all storms during the simulation. To calculate the enrichment ratio, the value for _orgn\_enrich_ is set to 0. This is the default option.
{% endhint %}
