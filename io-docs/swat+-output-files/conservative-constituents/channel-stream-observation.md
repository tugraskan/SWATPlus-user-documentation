# Channel stream observation

The channel stream observation file lists daily flow, concentrations, and loads for the channels named in the input file `cs_streamobs`. Channel output is written when `cs_obs_file == 1` and `cs_db%num_cs > 0`. [Open and header lines](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_cha_read.f90#L65-L86), [daily call](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L593-L595), [daily write](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_str_output.f90#L20-L63)

* cs\_streamobs\_output

The file name has no extension. Its first header line reads "Daily concentrations and loads for specified channels". It has six sets of columns, and each set holds one value for every channel listed in `cs_streamobs`.

* The file begins with descriptive text lines, one for each set of columns, followed by a `channels:` line. It has no column-name row. [Header lines](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_cha_read.f90#L75-L84)
* The `channels:` line prints the label and then each channel number as an 8-character integer. [Channel line and format](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_cha_read.f90#L84)
* Each data row begins with two integer values, `time%yrc` and `time%day`, which have no printed header. The remaining values are the six sets of columns in the order of the table below. [Data row and format](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_str_output.f90#L63)
* The declaration of `cs_obs_file` gives it a default value of 0, and no other statement in this source revision assigns it. [Declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L351)

| Field | Description | Type | Unit |
| --- | --- | --- | --- |
|[year](channel-stream-observation/year.md)|Calendar year of the daily observation|Integer|none|
|[jday](channel-stream-observation/jday.md)|Julian day of the year for the daily observation|Integer|none|
| [flow rate (m3/sec)](channel-stream-observation/flow.md) | Flow rate in each listed channel | real | m3/sec |
| [seo4 conc (g/m3)](channel-stream-observation/seo4.md) | Concentration of seo4 in each listed channel | real | g/m3 |
| [seo3 conc (g/m3)](channel-stream-observation/seo3.md) | Concentration of seo3 in each listed channel | real | g/m3 |
| [seo4 load (kg/day)](channel-stream-observation/seo4_load.md) | Load of seo4 in each listed channel | real | kg/day |
| [seo3 load (kg/day)](channel-stream-observation/seo3_load.md) | Load of seo3 in each listed channel | real | kg/day |
| [no3n load (kg/day)](channel-stream-observation/no3n_load.md) | Nitrate load in each listed channel | real | kg/day |
