---
description: "Phreatophyte area in the cell, m²"
---

# gw_phyt_area

**Code reference:** `gw_phyt_area(i)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L431), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1450)).

Area covered by phreatophytes in the cell, in m². Daily uptake is computed as ([`gwflow_phreatophyte.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_phreatophyte.f90#L36)):

$$Q = r \, A$$

where $Q$ is daily phreatophyte uptake ($\text{m}^3/\text{day}$), $r$ is the rate from [phreato.gw](../phreato.gw/gw_phyt_rate.md) for the current water-table depth (`m/day`), and $A$ is `gw_phyt_area` ($\text{m}^2$).
