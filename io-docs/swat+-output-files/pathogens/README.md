# Pathogen Outputs

Pathogen output is written only when pathogens are configured and the corresponding output option is enabled. HRU files are named `hru_path_day`, `hru_path_mon`, `hru_path_yr`, and `hru_path_aa`, with `.txt` and `.csv` variants.

{% hint style="warning" %}
In the inspected main version, each pathogen data row writes 18 values under a 15-heading header. The `apply_kg/h` and `decay_kg/h` positions therefore do not provide a complete one-to-one label for the application, regrowth, die-off, and wash values that are written.
{% endhint %}

| Field | Description | Unit |
| --- | --- | --- |
| [jday](jday.md) | Day of year | n/a |
| [mon](mon.md) | Month | n/a |
| [day](day.md) | Day of month | n/a |
| [yr](yr.md) | Calendar year | n/a |
| [unit](unit.md) | HRU identifier | n/a |
| [gis_id](gis_id.md) | GIS identifier | n/a |
| [name](name.md) | HRU name | n/a |
| [plant_kg/h](plant_kg-per-h.md) | Pathogen mass on plant material | kg/h |
| [soil_kg/h](soil_kg-per-h.md) | Pathogen mass in soil | kg/h |
| [sed_kg/h](sed_kg-per-h.md) | Pathogen transported with sediment | kg/h |
| [surq_kg/h](surq_kg-per-h.md) | Pathogen transported in surface runoff | kg/h |
| [latq_kg/h](latq_kg-per-h.md) | Pathogen transported in lateral flow | kg/h |
| [perc_kg/h](perc_kg-per-h.md) | Pathogen transported by percolation | kg/h |
| [apply_kg/h](apply_kg-per-h.md) | Pathogen applied | kg/h |
| [decay_kg/h](decay_kg-per-h.md) | Pathogen lost through decay | kg/h |

The unit text above reproduces the printed headings. The source writes one row per configured pathogen, so row identity must be read with the model's pathogen configuration.

Pathogen hydrograph streams use `hydin_paths_*` and `hydout_paths_*`. Those dynamic constituent-stream files are documented with the other [Hydrologic Constituent Streams](../hydrologic-constituent-streams/README.md).
