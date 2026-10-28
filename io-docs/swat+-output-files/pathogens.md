# Pathogen Outputs

Pathogen output is written only when pathogens are configured and the corresponding output option is enabled. HRU files are named `hru_path_day`, `hru_path_mon`, `hru_path_yr`, and `hru_path_aa`, with `.txt` and `.csv` variants.

| Field | Description | Unit |
| --- | --- | --- |
| jday | Day of year | n/a |
| mon | Month | n/a |
| day | Day of month | n/a |
| yr | Calendar year | n/a |
| unit | HRU identifier | n/a |
| gis_id | GIS identifier | n/a |
| name | HRU name | n/a |
| plant_kg/h | Pathogen mass on plant material | kg/h |
| soil_kg/h | Pathogen mass in soil | kg/h |
| sed_kg/h | Pathogen transported with sediment | kg/h |
| surq_kg/h | Pathogen transported in surface runoff | kg/h |
| latq_kg/h | Pathogen transported in lateral flow | kg/h |
| perc_kg/h | Pathogen transported by percolation | kg/h |
| apply_kg/h | Pathogen applied | kg/h |
| decay_kg/h | Pathogen lost through decay | kg/h |

The unit text above reproduces the printed headings. The source writes one row per configured pathogen, so row identity must be read with the model's pathogen configuration.

Pathogen hydrograph streams use `hydin_paths_*` and `hydout_paths_*`. Those dynamic constituent-stream files are documented with the other [Hydrologic Constituent Streams](hydrologic-constituent-streams.md).
