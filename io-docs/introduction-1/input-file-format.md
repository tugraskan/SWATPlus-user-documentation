---
description: General formatting rules, title/header conventions, and Fortran list-directed parsing behavior for SWAT+ input files.
---

# Input File Format

## Free-Format Space-Delimited Layout

Nearly all SWAT+ input files are plain text parsed with Fortran list-directed input (`read(unit, *)`), so columns are separated by whitespace rather than fixed column widths.

* **Positional reading:** SWAT+ reads values strictly by column position, not by matching header names. Every preceding column on a row must contain a token; omitting a value causes Fortran list-directed I/O to continue onto the next line and misalign subsequent rows. Extra trailing tokens on fixed-column rows are discarded unless the reader parses a variable-length list.
* **Strings with spaces or `/`:** Unquoted strings cannot contain spaces (whitespace splits tokens) or forward slashes `/` (which terminate a Fortran list-directed read early). Quote paths or text containing spaces or `/` (`"..."` or `'...'`), except on lines explicitly read as raw text (`'(A)'`), such as the optional output-directory row at the end of [`file.cio`](master-file-file.cio.md) ([`readcio_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readcio_read.f90#L102-L103)).
* **`null` placeholder:** Optional filenames and cross-file references use lowercase `null` (most readers perform a case-sensitive check against `"null"`).

## Title and Header Lines

* **Line 1 (Title):** Reserved for a descriptive title (SWAT+ Editor writes the filename, Editor version, and timestamp). SWAT+ reads line 1 into a dummy variable (`titldum`, typically `character(len=80)`, e.g., [`readcio_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readcio_read.f90#L8-L24) and [`time_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_read.f90#L10-L24)) and discards it. **Do not leave line 1 (or line 2) blank** in standard list-directed files: Fortran `read(unit, *)` skips blank lines and consumes the next non-blank line as `titldum`, shifting the file up by one line. (Only readers using formatted `'(a)'` input, such as [`carbon_bsn_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_bsn_read.f90#L65-L71), tolerate blank title/header lines.) The title line is not strictly truncated at 80 characters on disk—list-directed input reads only the first token into the 80-character buffer and advances to the next record—but keeping the title short and non-empty on one line is good practice.
* **Line 2 (Column Header):** Most tabular input files reserve line 2 for column names, which are read into a dummy `header` variable and ignored by the model.
* **Layout exceptions:**
  * [`file.cio`](master-file-file.cio.md) has a title line and **no** column header line ([`readcio_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readcio_read.f90#L24-L26)).
  * Multi-section or structured files use additional headers or count lines, such as [`print.prt`](simulation-settings/print.prt/README.md) ([`basin_print_codes_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_print_codes_read.f90#L24-L48)), [`constituents.cs`](constituents/constituents.cs.md) (alternating count and name rows with no column headings), [`chan-surf.lin`](connectivity/chan_surf.lin.md) (title, record count, then header), decision tables (`*.dtl`), and weather station time-series files (title, header, station metadata row, then observations).
  * Many table readers make two passes (counting records or finding the maximum `id` to allocate arrays, then rewinding to read rows, e.g., [`hru_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_read.f90#L49-L65)), so avoid inserting comments or stray lines inside data blocks.

## File Discovery

Core input filenames are listed in [`file.cio`](master-file-file.cio.md) (falling back to the defaults in [`input_file_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/input_file_module.f90#L8-L278)), whereas several optional modules (such as [GWFlow](modflow.md), auxiliary `.wal` [Water Allocation](water-allocation/README.md) files, salt and general-constituent working-directory files, `carbon_lyr.bsn`, `shade_factor.shf`, and `scen_dtl.upd`) are opened directly by fixed filename in the simulation working directory (`TxtInOut`).
