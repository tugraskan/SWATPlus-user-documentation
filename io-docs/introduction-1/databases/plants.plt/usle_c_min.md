---
description: Minimum value of the USLE C factor for water erosion
---

# usle\_c\_min

**Code reference:** `pldb(ic)%usle_c` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/plant_data_module.f90#L69)).

The minimum C factor can be estimated from a known average annual C factor using the following equation (Arnold and Williams, 1995):

$$C_{USLE,mn} = 1.463 * ln⁡[C_{USLE,aa}] + 0.1034$$

where $$C_{USLE,mn}$$ is the minimum C factor for the land cover and $$C_{USLE,aa}$$ is the average annual C factor for the land cover.&#x20;

#### References

> Arnold and Williams (1995)
