# GWFlow Basin Water Balance

This report summarizes groundwater storage and water exchanges across the basin's active GWFlow cells. Water volumes are expressed as equivalent depths over the total basin area, making the exchanges comparable with other basin water-balance results. The daily file and the three longer-period files have distinct schemas.

## How to produce these files

Set `gwflow = 1` in [codes.bsn](../../introduction-1/basin-1/codes.bsn/README.md). In [print.prt](../../introduction-1/simulation-settings/print.prt/README.md), set `use_obj_lbls = y` and enable the desired periods on `gwflow_wb`. For example, `gwflow_wb y n n n` selects daily output. If the row is omitted, the periods come from `write_day`, `write_mon`, `write_yr`, and `write_aa` in [codes.gw](../../introduction-1/gwflow/codes.gw/README.md). [GWFlow activation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_objs.f90#L46), [Print flag overrides](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L254)

| File | Schema |
| --- | --- |
| `gwflow_basin_wb_day.txt` | [Daily basin water balance](daily-basin-water-balance.md), 31 columns |
| `gwflow_basin_wb_mon.txt`, `gwflow_basin_wb_yr.txt`, `gwflow_basin_wb_aa.txt` | [Monthly, yearly, and average-annual basin water balance](longer-period-basin-water-balance.md), shared 26-column schema |
