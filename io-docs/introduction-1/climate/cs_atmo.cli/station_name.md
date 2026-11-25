---
description: "Station identifier for the annual timestep record (station_name)"
---

# station_name

**Code reference:** `station_name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_read_atmodep_cs.f90#L20)).

Station token parsed as a real number at the start of every station block. SWAT+ assigns records by station order in [atmo.cli](../atmo.cli/README.md).

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).* See [cli_read_atmodep_cs.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_read_atmodep_cs.f90#L46-L93).
