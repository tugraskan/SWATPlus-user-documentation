# Salt Outputs

SWAT+ can report salt balances for the basin, routing units, HRUs, channels, aquifers, reservoirs, and wetlands. Configure the salt module and enable the corresponding print periods. Daily, monthly, yearly, and average-annual files use the suffixes `_day`, `_mon`, `_yr`, and `_aa`. Basin salt has TXT files only. See its schema page for how the file opener and writer handle the print settings.

The salt ions always appear in this order: sulfate (`so4`), calcium (`ca`), magnesium (`mg`), sodium (`na`), potassium (`k`), chloride (`cl`), carbonate (`co3`), and bicarbonate (`hco3`). Every name in the Field column below is an exact printed heading.

Daily, monthly, and yearly mass fields generally use kg. Concentrations generally use g/m3. Where available, the average-annual TXT preambles label mass transfers as kg/yr and sometimes use kg/yr for stored mass. See the individual schema pages for how those values are calculated.

The common identifying headings are `jday`, `mon`, `day`, `yr`, `unit`, and `gis_id`. Basin salt output instead begins with `yr`, `mo`, and `jday`.

## How to produce these files

Configure salts in the model. In [print.prt](../../introduction-1/simulation-settings/print.prt/README.md), set the desired daily, monthly, yearly, or average-annual columns to `y`. Use `basin_salt`, `ru_salt`, `hru_salt`, `channel_salt`, `aqu_salt`, and `res_salt` for basin, routing unit, HRU, channel, aquifer, and reservoir reports, respectively. Set `csvout` to `y` for CSV copies where the file opener uses that setting. [Print rows](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_print_codes_read.f90#L601), [File creation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_salt.f90#L17)

For `wetland_salt_*`, enable the same periods on both `wetland_salt` and `res_salt`. This source revision uses `wetland_salt` to open the files and `res_salt` to write the data rows. The file opener also requires a reservoir object, and wetland data rows require a full HRU with a wetland assignment. [Wetland file creation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_salt.f90#L853), [Wetland data writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_salt_output.f90#L41), [Wetland caller](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L473)

## File schemas

| File family | Schema |
| --- | --- |
| `basin_salt_*` | [Basin salt balance](basin-salt-balance.md) |
| `rout_unit_salt_*` | [Routing-unit salt balance](routing-unit-salt-balance.md) |
| `channel_salt_*` | [Channel salt](channel-salt.md) |
| `aqu_salt_*` | [Aquifer salt](aquifer-salt.md) |
| `reservoir_salt_*`, `wetland_salt_*` | [Reservoir and wetland salt](reservoir-wetland-salt.md) |
