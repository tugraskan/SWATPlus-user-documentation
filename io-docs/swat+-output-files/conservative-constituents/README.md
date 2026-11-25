# Conservative Constituents

Conservative-constituent output tracks selenate (`seo4`), selenite (`seo3`), and boron (`born`). Daily, monthly, yearly, and average-annual files use `_day`, `_mon`, `_yr`, and `_aa`. The [basin balance](basin-balance.md) has TXT files and its own rules for when the writer emits rows.

All object-level files begin with `jday`, `mon`, `day`, `yr`, `unit`, and `gis_id`. The remaining printed headings differ by object type.

## How to produce these files

Configure the conservative constituents in the model. In [print.prt](../../introduction-1/simulation-settings/print.prt/README.md), set the desired daily, monthly, yearly, or average-annual columns to `y`. The row names are `basin_cs`, `hru_cs`, `ru_cs`, `aqu_cs`, `channel_cs`, and `res_cs` for basin, HRU, routing unit, aquifer, channel, and reservoir output, respectively. Set `csvout` to `y` for the CSV variants. [Print rows](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_print_codes_read.f90#L658), [File creation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L17)

In this source revision, `res_cs` also controls file creation and data rows for `wetland_cs_*`. The parser accepts `wetland_cs`, but that row alone does not activate these files. The wetland file opener checks for at least one reservoir object. Wetland data rows require a full HRU with a wetland assignment. [Wetland print row](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_print_codes_read.f90#L706), [Wetland file creation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L881), [Wetland data writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_cs_output.f90#L43), [Wetland caller](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L473)

## File schemas

| File family | Schema |
| --- | --- |
| `hru_cs_*` | [HRU](hru.md) |
| `rout_unit_cs_*` | [Routing unit](routing-unit.md) |
| `channel_cs_*` | [Channel](channel.md) |
| `cs_streamobs_output` | [Channel stream observation](channel-stream-observation.md) |
| `aquifer_cs_*` | [Aquifer](aquifer.md) |
| `reservoir_cs_*` | [Reservoir](reservoir.md) |
| `wetland_cs_*` | [Wetland](wetland.md) |
| `basin_cs_*` | [Basin balance](basin-balance.md) |

See [reservoir and wetland](reservoir-wetland.md) for how the two reports use the same print setting.
