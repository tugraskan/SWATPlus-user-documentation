---
description: Name of the precipitation station
---

# pcp

**Code reference:** `wst(i)%wco_c%pgage` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/climate_module.f90#L118)).

The name of the precipitation station is a foreign key referencing the filenames listed in [**pcp.cli**](../pcp.cli-and-precipitation-data-files.md).

{% hint style="info" %}
If "sim" is entered instead of a precipitation station name, the model will generate daily precipitation values using the weather generator station specified in column [wgn](wgn.md).
{% endhint %}

An unmatched filename logs a warning and leaves the index at zero. Use the exact listed filename for measured data or sim to select generation. See [cli_staread.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_staread.f90#L73-L88).
