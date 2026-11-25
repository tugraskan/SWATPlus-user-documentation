# Land-use change records

SWAT+ opens `lu_change_out.txt` during output initialization. The file has no separate print switch. Its rows come from the decision-table actions listed below, so it can contain only a title and headings if none of those actions runs. The report is TXT. [Output initialization](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/proc_open.f90#L10), [File opener](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_lu_change.f90#L7)

The printed headings are `hru`, `year`, `mon`, `day`, `operation`, `lu_before`, and `lu_after`. The first five values identify the HRU, date, and operation. The last four visible fields depend on the operation. Every action below writes nine visible fields when the space-separated placeholders are read separately. There are no headings for fields 8 and 9. [Header](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_lu_change.f90#L10), [Action writes](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L999)

| Operation | Fields 6 and 7 under `lu_before` and `lu_after` | Unheaded fields 8 and 9 |
| --- | --- | --- |
| `LU_CHANGE` | Previous and new land-use management names | `0`, `0` |
| `SNOW_CHANGE` | Previous and new snow parameter set names | `0`, `0` |
| `HRU_FRACTION_CHANGE` | Filenames for the updated LSU and routing-unit element tables, in that order | `0`, `0` |
| `P_FACTOR`, `CONTOUR`, `STRIPCROP`, `TERRACE` | `null`, `null` | Previous and new USLE support-practice factor, dimensionless |
| `TILE_INSTALL` | Tile-drain name of the HRU's current `tiledrain` entry, then the name found for the action's `file_pointer` | `0`, `0` |
| `SEPTIC_INSTALL`, `FSTRIP_INSTALL`, `GRASSWW_INSTALL`, `USER_DEF_BMP` | The action's `file_pointer`, then the name found for it in that structure's database (septic, filter strip, grassed waterway, user BMP) | `0`, `0` |
| `GRASSWW_UNINSTALL` | Name of the HRU's current grassed waterway, then `null` | `0`, `0` |

For `HRU_FRACTION_CHANGE`, the writer prints the current value of `j` without assigning it from the action. That row's first value cannot reliably identify the HRUs affected by the update. The two filenames identify the inputs passed to the fraction-update routine. [Fraction change action](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L999), [Fraction update inputs](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_fr_change.f90#L1)

On SWAT+ dev each structural action logs names from its own database ([structural action writers](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L1135-L1253)). When the `file_pointer` is not found, the index is set to 0 before logging. Two cases still need care:

- `TILE_INSTALL` logs the HRU's current `tiledrain` index without a range check ([`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L1151-L1155)).
- In `GRASSWW_INSTALL` the line that stores the found index is commented out, so the index passed to the structure setup and logged is whatever value it already held ([`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L1208-L1223)). The logged name, and the waterway installed, may not match `file_pointer`. This comes from source reading.

[Back to Management](README.md).
