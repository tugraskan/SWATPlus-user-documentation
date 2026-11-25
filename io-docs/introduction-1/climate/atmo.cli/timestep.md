---
description: Time step of the atmospheric deposition data
---

# timestep

**Code reference:** `atmodep_cont%timestep` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/climate_module.f90#L210)).

| Option | Description    |
| ------ | -------------- |
| mo     | Monthly        |
| yr     | Yearly         |
| aa     | Average annual |

The reader treats this field as a two-character code. The same code also selects the layout in [cs_atmo.cli](../cs_atmo.cli/README.md) and [salt_atmo.cli](../salt_atmo.cli/README.md). See [cli_read_atmodep.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_read_atmodep.f90#L36-L37).
