---
description: Groundwater revap coefficient
---

# revap

**Code reference:** `aqudb(i)%revap_co` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/aquifer_module.f90#L17)).

Water may move from the aquifer into the overlying unsaturated zone. In periods when the material overlying the aquifer is dry, water in the capillary fringe that separates the saturated and unsaturated zones will evaporate and diffuse upward. As water is removed from the capillary fringe by evaporation, it is replaced by water from the underlying aquifer. Water may also be removed from the aquifer by deep-rooted plants that are able to uptake water directly from the aquifer. This process is significant in watersheds where the saturated zone is not very far below the surface or where deep-rooted plants are growing.

As _revap_ approaches 0, movement of water from the aquifer to the root zone is restricted. As _revap_ approaches 1, the rate of transfer from the aquifer to the root zone approaches the rate of potential evapotranspiration.
