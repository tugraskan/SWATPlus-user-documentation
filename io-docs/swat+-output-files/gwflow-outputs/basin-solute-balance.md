# Gwflow solute balance, average annual

The gwflow average annual solute balance files are written when solute output is active in gwflow (`gw_solute_flag == 1`) and the average annual solute flag is on (`gwflag_solute_aa == 1`). When `print.prt` has a `gwflow_solute` line, `gwflag_solute_aa` is 1 only if its average-annual column is `y`. One file is written for each solute, and each file receives one data row when the last simulation day is reached. [Flag assignment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L299-L306), [file setup](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L443-L470), [call at simulation end](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_simulate.f90#L471-L474), [row write](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L2137-L2151)

The file for solute number `n` takes the n-th name in this list:

* gwflow\_basin\_sol\_no3\_aa.txt
* gwflow\_basin\_sol\_p\_aa.txt
* gwflow\_basin\_sol\_so4\_aa.txt
* gwflow\_basin\_sol\_ca\_aa.txt
* gwflow\_basin\_sol\_mg\_aa.txt
* gwflow\_basin\_sol\_na\_aa.txt
* gwflow\_basin\_sol\_k\_aa.txt
* gwflow\_basin\_sol\_cl\_aa.txt
* gwflow\_basin\_sol\_co3\_aa.txt
* gwflow\_basin\_sol\_hco3\_aa.txt
* gwflow\_basin\_sol\_seo4\_aa.txt
* gwflow\_basin\_sol\_seo3\_aa.txt

The first two names are always set. Names 3 to 10 are set only when `cs_db%num_salts > 0`, and names 11 and 12 only when `cs_db%num_cs > 0`. The number of solutes is 2, plus `cs_db%num_salts` and `cs_db%num_cs` when `constituents.cs` exists. [File names](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L445-L461), [Solute count](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1587-L1601)

* Each file starts with the line "Solute basin average annual loads (kg):" followed by the solute name, then a heading line and a units line. [Header lines](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L462-L470)
* The heading line has 27 entries. The units line has the same count, with blanks for the first seven and `kg` for the last twenty.
* Each of the last twenty values is the accumulated total divided by `nbyr_r`, the number of simulation years. [Division](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L2117-L2136), [nbyr\_r](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1985)
* The twenty values are matched to their headings by position: the n-th heading after `name` labels the n-th value after `name` in the write statement. [Headings](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L463-L467), [Values](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L2138-L2151)
* The `unit` and `gis_id` columns hold the literal constant `       1` in every row.

| Field | Description | Type | Unit |
| --- | --- | --- | --- |
| [jday](basin-solute-balance/jday.md) | Day value of the last simulation day | integer | n/a |
| [mon](basin-solute-balance/mon.md) | Month of the last simulation day | integer | n/a |
| [day](basin-solute-balance/day.md) | Day of the month | integer | n/a |
| [yr](basin-solute-balance/yr.md) | Calendar year | integer | n/a |
| [unit](basin-solute-balance/unit.md) | Constant 1 | string | n/a |
| [gis\_id](basin-solute-balance/gis_id.md) | Constant 1 | string | n/a |
| [name](basin-solute-balance/name.md) | SWAT+ basin name | string | n/a |
| [delm](basin-solute-balance/delm.md) | Average annual value in the `delm` column | real | kg |
| [recharge](basin-solute-balance/recharge.md) | Average annual value in the `recharge` column | real | kg |
| [gw\_sw](basin-solute-balance/gw_sw.md) | Average annual value in the `gw_sw` column | real | kg |
| [sw\_gw](basin-solute-balance/sw_gw.md) | Average annual value in the `sw_gw` column | real | kg |
| [sat\_excess](basin-solute-balance/sat_excess.md) | Average annual value in the `sat_excess` column | real | kg |
| [soil](basin-solute-balance/soil.md) | Average annual value in the `soil` column | real | kg |
| [advection](basin-solute-balance/advection.md) | Average annual value in the `advection` column | real | kg |
| [dispersion](basin-solute-balance/dispersion.md) | Average annual value in the `dispersion` column | real | kg |
| [react\_in](basin-solute-balance/react_in.md) | Average annual value in the `react_in` column | real | kg |
| [react\_out](basin-solute-balance/react_out.md) | Average annual value in the `react_out` column | real | kg |
| [mineral](basin-solute-balance/mineral.md) | Average annual value in the `mineral` column | real | kg |
| [sorption](basin-solute-balance/sorption.md) | Average annual value in the `sorption` column | real | kg |
| [pump\_allo](basin-solute-balance/pump_allo.md) | Average annual value in the `pump_allo` column | real | kg |
| [pump\_ext](basin-solute-balance/pump_ext.md) | Average annual value in the `pump_ext` column | real | kg |
| [tile](basin-solute-balance/tile.md) | Average annual value in the `tile` column | real | kg |
| [reservoir](basin-solute-balance/reservoir.md) | Average annual value in the `reservoir` column | real | kg |
| [wetland](basin-solute-balance/wetland.md) | Average annual value in the `wetland` column | real | kg |
| [canal](basin-solute-balance/canal.md) | Average annual value in the `canal` column | real | kg |
| [floodplain](basin-solute-balance/floodplain.md) | Average annual value in the `floodplain` column | real | kg |
| [pond](basin-solute-balance/pond.md) | Average annual value in the `pond` column | real | kg |
