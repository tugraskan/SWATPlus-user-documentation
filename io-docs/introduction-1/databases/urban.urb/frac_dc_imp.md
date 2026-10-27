---
description: Fraction of directly connected impervious area in urban land type
---

# frac\_dc\_imp

**Code reference:** `urbdb(iu)%fcimp`

**Declared type:** `urban_db` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/urban_parm_read.f90#L42), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/urban_data_module.f90#L8)).

Impervious areas can be differentiated into two groups, the area that is hydraulically connected to the drainage system and the area that is not directly connected. As an example, assume there is a house surrounded by a yard where runoff from the roof flows into the yard where it infiltrates into the soil. The rooftop is impervious, but it is not hydraulically connected to the drainage system. In contrast, a parking lot whose runoff enters a storm water drain is hydraulically connected.&#x20;

When modeling urban areas, the connectedness of the drainage system must be quantified. The best methods for determining the fraction total and directly connected impervious areas is to conduct a field survey or analyze aerial photographs.
