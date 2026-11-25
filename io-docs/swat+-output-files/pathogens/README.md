# Pathogen Outputs

HRU pathogen files are `hru_path_day.txt`, `hru_path_mon.txt`, `hru_path_yr.txt`, and `hru_path_aa.txt`, plus corresponding `.csv` names. Their opener uses the `hru_wb` row of `print.prt` (`pco%wb_hru%d/m/y/a`) and `cs_db%num_tot > 0`, rather than a separate pathogen print option. Because the test counts all constituents, files can be opened with headers even when no pathogens are configured. Actual data rows iterate over `cs_db%num_paths` ([opener](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_path.f90#L11); [writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_pathogen_output.f90#L28)).

{% hint style="warning" %}
Each data row writes 18 values under a 15-heading header. The first seven fields identify the HRU and date; the following 11 values are the pathogen-balance record. In particular, `decay_kg/h` labels plant application, not die-off. Three further process values have no printed headings. These source defects affect both TXT and CSV layouts.
{% endhint %}

## Literal printed headings and actual values

The headings below retain the exact printed text. Descriptions follow the corresponding written component, including inactive or stale diagnostics.

| Field | Description | Unit |
| --- | --- | --- |
| [jday](jday.md) | Day of year | n/a |
| [mon](mon.md) | Month | n/a |
| [day](day.md) | Day of month | n/a |
| [yr](yr.md) | Calendar year | n/a |
| [unit](unit.md) | HRU identifier | n/a |
| [gis_id](gis_id.md) | GIS identifier | n/a |
| [name](name.md) | HRU name | n/a |
| [plant_kg/h](plant_kg-per-h.md) | Plant diagnostic initialized from the input value; not refreshed from current foliage | unresolved |
| [soil_kg/h](soil_kg-per-h.md) | Soil diagnostic with no identified producer; default zero | unresolved |
| [sed_kg/h](sed_kg-per-h.md) | Sediment-associated pathogen diagnostic, conditionally updated | unresolved |
| [surq_kg/h](surq_kg-per-h.md) | Surface-runoff diagnostic overwritten with the nonnegative surface-soil pool | unresolved |
| [latq_kg/h](latq_kg-per-h.md) | Lateral-flow component with no identified producer; default zero | unresolved |
| [perc_kg/h](perc_kg-per-h.md) | Pathogen removed from soil layer 1 by the percolation calculation | unresolved |
| [apply_kg/h](apply_kg-per-h.md) | Soil-application component with no identified producer; default zero | unresolved |
| [decay_kg/h](decay_kg-per-h.md) | Plant-application component with no identified producer; default zero | unresolved |

The remaining data positions have no printed headings:

| Data position | Written component | Description |
| --- | --- | --- |
| 16 | [regro](regro.md) | Regrowth component with no identified producer; default zero |
| 17 | [die_off](die_off.md) | Net soil/foliage die-off; negative values represent net regrowth |
| 18 | [wash](wash.md) | Pathogen washed from foliage to surface soil |

These three component names identify source values; they are not additional headings present in the file. The writer prints one row per pathogen in configured order, but includes no pathogen name or index. Repeated HRU/date identifiers alone do not distinguish pathogen species ([record declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_ls_pathogen_module.f90#L5); [write loop](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_pathogen_output.f90#L28)).

## Units and diagnostic limits

The printed `kg/h` suffix is not a verified per-hour unit. All 11 balance declarations say `kg/ha`, while the underlying `constituent_mass%path` state is annotated `cfu` (colony-forming units). The initialization and process routines do not establish a consistent count-to-mass or area conversion for these output components. Their physical units remain unresolved; silently relabeling every column kg/ha would hide the conflict ([balance units](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_ls_pathogen_module.f90#L8); [state units](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L81)).

The source establishes how these values relate to one another, even though it does not establish a common physical unit.

| Field or position | Unit evidence |
| --- | --- |
| `plant_kg/h` | Direct copy of the initial plant entry. The shared input-state declaration allows `ppm` or `cfu/m²`, and the HRU reader and initializer apply no conversion. [Declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L287-L296), [Reader](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/path_hru_aqu_read.f90#L41-L61), [Copy](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/pathogen_init.f90#L54-L73) |
| `surq_kg/h`, `perc_kg/h` | The final runoff value copies the nonnegative soil pool. Percolation is capped at that pool and subtracted directly. Both are expressed on the soil pool's numerical basis. [Runoff](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/path_ls_runoff.f90#L24-L35), [Percolation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/path_ls_swrouting.f90#L19-L28) |
| `sed_kg/h` | Derived from the remaining soil pool, sediment yield, and HRU area. The equation uses a fixed scale factor, but the source does not define an input basis that establishes a physical unit for the result. [Sediment calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/path_ls_runoff.f90#L33-L37) |
| Positions 17 and 18 | `die_off` combines changes in the foliage and soil pools. `wash` is transferred directly from foliage to soil. Neither operation converts between the pool bases. [Pool transfers and differences](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/path_ls_process.f90#L30-L71) |
| Unassigned diagnostics | Their zero defaults provide no independent evidence of a physical unit. [Record defaults](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_ls_pathogen_module.f90#L5-L19) |

The `plant` diagnostic is initialized from `path_soil_ini%plt` but is not subsequently refreshed from the evolving foliage state. No active producer was identified for `soil`, `latq`, `apply_sol`, `apply_plt`, or `regro`; these components retain their declared zero defaults in the inspected paths. The actual process routines update `cs_soil` and `cs_pl`, so a zero or stale output diagnostic does not demonstrate an absent soil or foliage pathogen pool. [initialization](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/pathogen_init.f90#L56-L79), [process state](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/path_ls_process.f90#L30-L71).

## Initialization and routing

- **Soil and foliage values at startup.** The reader loads the soil and plant entries from the configured `path_hru.ini` table directly into two arrays. The HRU resolves the named initialization record, and the initializer copies its plant entry only to the printed diagnostic. It allocates the live foliage pool at zero. In the soil-layer loop, layer 1 receives the configured value. Every later layer iteration writes zero to **layer 1** again, so multilayer HRUs finish initialization with that soil value cleared. [table reader](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/path_hru_aqu_read.f90#L41-L61), [name lookup](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_read.f90#L100-L106), [allocation and assignments](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/pathogen_init.f90#L54-L79).
- **Which parameter record the diagnostics use.** The daily process loops over pathogen slots when updating the soil and foliage state. It selects the process parameters using the HRU's soil-and-plant initialization record index for every slot. Rows can therefore represent different state slots while sharing the same parameter record. [initialization index lookup](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_read.f90#L100-L106), [process and state indices](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/path_ls_process.f90#L30-L68).
- **Daily HRU diagnostics and hydrographs.** The HRU runs percolation first, then surface runoff, then the foliage and soil process. The later process can change the pools after the runoff and percolation diagnostics have been set. The HRU hydrograph builder writes zero into its pathogen fields for surface runoff, percolation, lateral flow, tile flow and total flow. In this revision the printed loss diagnostics do not carry a pathogen payload to downstream objects through those fields. [daily call order](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L582-L587), [component hydrographs](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_hyds.f90#L92-L148), [total hydrograph](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_hyds.f90#L174-L178).

In the surface-runoff routine, a calculated and capped runoff value is immediately overwritten by `Max(cs_soil(j)%ly(1)%path(ipath), 0.)`. That value is then removed from the soil pool before sediment-associated transport is calculated. The table therefore describes the value actually assigned, without certifying it as a valid transport calculation. The sediment diagnostic is updated only inside `enratio > 0`, with no reset in that routine when the condition fails ([runoff assignments](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/path_ls_runoff.f90#L24)).

## Reporting periods and CSV format

- The writer starts after the `nyskip` years in `print.prt`. The daily print window and interval restrict daily rows, while monthly accumulation still runs on every day passed to the writer. If the run begins after the first day of a month, the first monthly `plant` mean still divides its sum by the full calendar month's length. [warm-up gate](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/command.f90#L440-L485), [daily gate and month divisor](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_pathogen_output.f90#L27-L45).
- The addition operator omits `latq` and `wash`, so their contributions are not accumulated.
- The `//` averaging operator assigns only `plant` and `soil`; all other result components retain zero defaults. Monthly output applies it using calendar-month days, discarding transport, application, regrowth, die-off, and wash values rather than retaining their totals.
- The writer transfers each monthly `plant` and `soil` mean into the yearly accumulator only at calendar month end. A final partial month contributes to neither the yearly row nor the average-annual numerator, even when daily rows show those days. [Month-end transfer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_pathogen_output.f90#L30-L64)
- Yearly output divides the accumulated `plant` and `soil` means by 12 even when fewer months contribute. The yearly accumulator is not reset, so the previous year's scaled result is added to the next year's monthly means before division. For example, if the previous yearly `plant` value was 12 and the run ends in mid-January before any new month closes, the next yearly value is `12 / 12 = 1`. [Yearly scaling and carryover](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_pathogen_output.f90#L67-L85)
- Average-annual output sums those yearly results and divides by `time%yrs_prt`, which includes the final partial month's days in runs with no warm-up. The earlier data loss and carryover therefore affect the average-annual result as well. [Annual accumulation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_pathogen_output.f90#L67-L94), [Simulated-year divisor](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/time_control.f90#L134-L191)
- The `hru_path_aa.csv` header uses comma-separated formatting, but its data writer uses fixed-width format `100`, just like TXT. Do not assume that file has comma-separated data rows.

Source: [operators](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_ls_pathogen_module.f90#L77) and [period/CSV writes](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_pathogen_output.f90#L43). These are static source findings; their numerical consequences have not been tested in a model run.

Pathogen hydrograph streams use `hydin_paths_*` and `hydout_paths_*`. Those constituent-stream reports remain documented with the other [Hydrologic Constituent Streams](../hydrologic-constituent-streams/README.md); this HRU review does not validate those separate writers.
