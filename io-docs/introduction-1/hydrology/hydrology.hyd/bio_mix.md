---
description: Biological mixing efficiency
---

# bio\_mix

**Code reference:** `hyd_db(ithyd)%biomix` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hydrology_data_module.f90#L18)).

Biological mixing is the redistribution of soil constituents as a result of the activity of biota in the soil (e.g. earthworms, etc.). Studies have shown that biological mixing can be significant in systems where the soil is only infrequently disturbed. In general, as a management system shifts from conventional tillage to conservation tillage to no-till there will be an increase in biological mixing.&#x20;

SWAT+ allows biological mixing to occur to a depth of 300 mm (or the bottom of the soil profile if it is shallower than 300 mm). The efficiency of biological mixing is defined by the user and is conceptually the same as the mixing efficiency of a tillage implement. The redistribution of nutrients by biological mixing is calculated using the same methodology as that used for a tillage operation. Biological mixing is performed at the end of every calendar year.
