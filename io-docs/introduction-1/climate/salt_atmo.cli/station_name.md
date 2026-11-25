---
description: "The identifier of the weather station associated with the annual atmospheric salt deposition record"
---

# station_name

**Code reference:** `station_name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_read_atmodep_salt.f90#L15)).

Station label read as text up to 15 characters at the start of every station block. SWAT+ assigns records by station order in [atmo.cli](../atmo.cli/README.md).

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).* See [cli_read_atmodep_salt.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_read_atmodep_salt.f90#L46-L93).
