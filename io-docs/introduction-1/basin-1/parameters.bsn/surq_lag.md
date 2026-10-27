---
description: Surface runoff lag time
---

# surq\_lag

**Code reference:** `bsn_prm%surlag` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/basin_module.f90#L82)).

In large routing units with a time of concentration greater than 1 day, only a portion of the surface runoff will reach the main channel on the day it is generated. SWAT+ incorporates a surface runoff storage feature to lag a portion of the surface runoff release to the main channel.&#x20;

This parameter controls the fraction of the total available water that will be allowed to enter the reach on any one day. For a given time of concentration, as _surq\_lag_ decreases in value more water is held in storage. The delay in release of surface runoff will smooth the streamflow hydrograph simulated in the reach.
