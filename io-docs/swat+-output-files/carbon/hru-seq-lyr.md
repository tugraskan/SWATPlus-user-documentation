# Legacy HRU sequestered soil carbon

Files `hru_seq_lyr.txt` and `hru_seq_lyr.csv` contain one row per full HRU per selected reporting event. Enable the desired daily, monthly, or yearly periods on the named `hru_cb` row in [print.prt](../../introduction-1/simulation-settings/print.prt/README.md). Both `y` and lowercase `l` write these rows. For example, `hru_cb n n y n` writes yearly snapshots. Set `csvout` to `y` for the CSV copy. The same file holds all selected periods, and the rows are snapshots on the reporting date. [File opener](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_legacy_module.f90#L472), [Reporting calls](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L539-L548)

## Column order

The writer prints the column headings once using the first HRU's layer-bottom depths, truncated to integer mm. Each HRU row has nine fixed values followed by one value per layer in that HRU. If HRUs have different layer depths or counts, the header can mislabel layers or have a different width from later rows. [Heading and row writes](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_write_historical.f90#L279)

The CSV header write inserts the first HRU's numeric 300 mm stock, in kg/ha, immediately after the `Seq_300mm_c` text and before writing the layer-depth labels. The data row has one 300 mm stock value in Mg/ha, then the layer values. Use the data positions below when reading the CSV. [CSV header and row writes](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_write_historical.f90#L286)

| Printed heading | Value | Unit |
| --- | --- | --- |
| `freq` | Reporting event (`day`, `mon`, or `year`) | — |
| `jday` | Day of year | — |
| `mon` | Month | — |
| `day` | Day of month | — |
| `year` | Calendar year | — |
| `unit` | HRU number | — |
| `hru` | Object type | — |
| `name` | HRU name | — |
| `Seq_300_sum` in TXT, `Seq_300mm_c` in CSV | Carbon stock in the top 300 mm | Mg/ha |
| Layer-bottom depths | Carbon stock in each whole layer, in order from the surface | Mg/ha |

## Carbon calculation

The 300 mm value adds whole layers within that depth and prorates any layer that crosses 300 mm by the fraction of its thickness above that boundary. The writer converts both the 300 mm value and the layer values from kg/ha to Mg/ha. With `carbon = 0`, both legacy stock reports use active humus, stable humus, and microbial biomass. With `carbon = 2`, this report uses passive humus, slow humus, and microbial biomass. [300 mm calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_write_historical.f90#L254), [Carbon pool assignments](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cbn_zhang2.f90#L1022)

[Back to the hru_cb reports](output-files-generated-by-hru_cb.md).
