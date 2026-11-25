# Crop Yield Reports

Crop-yield output is yearly or average annual rather than daily or monthly. The `crop_yld` control in [print.prt](../../introduction-1/simulation-settings/print.prt/README.md) uses `y` for yearly, `a` for average annual, `b` for both, and `n` for neither in the source declaration. Set `csvout = y` for the HRU CSV files. This page describes SWAT+ main `6f515368525e7d84089ae0f9d33f4c9115de5679`.

## Basin crop yield

`basin_crop_yld_yr.txt` and `basin_crop_yld_aa.txt` use the same six-column TXT layout:

| Field | Description | Unit |
| --- | --- | --- |
| `year` | Calendar year at the write | n/a |
| `plant_no` | Basin plant index | n/a |
| `plant_name` | Basin plant name | n/a |
| `harv_area` | Harvested area | ha |
| `yld` | Harvested yield mass | t |
| `yld_per_area` | Yield divided by harvested area plus the source's small denominator offset | t/ha |

The yearly values accumulate harvest area and yield across HRUs for each basin plant after skipped years. Average annual accumulates those yearly values, divides area and yield by `time%yrs_prt`, and retains the total-yield/total-area ratio.

{% hint style="warning" %}
At this revision, the basin opener creates both yearly and average-annual files only when `crop_yld` is `y` or `b`, and the average-annual writer uses the same `y`/`b` condition. The documented `a` control therefore does not by itself create or write the basin average-annual file. No basin crop-yield CSV opener is present in `header_yield.f90`.
{% endhint %}

[Basin file creation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_yield.f90#L20), [yearly and average-annual writes](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_control.f90#L279)

## HRU crop yield

The HRU TXT header for `crop_yld_yr.txt` and `crop_yld_aa.txt` describes ten scalar positions:

| Field | Description | Unit |
| --- | --- | --- |
| `jday` | Day of year at the write | n/a |
| `mon` | Month at the write | n/a |
| `day` | Day of month at the write | n/a |
| `yr` | Calendar year at the write | n/a |
| `unit` | HRU index | n/a |
| `PLANTNM` | Plant name | n/a |
| `MASS` | Average harvested total mass | kg/ha |
| `C` | Average harvested carbon mass | kg C/ha |
| `N` | Average harvested organic nitrogen mass | kg N/ha |
| `P` | Average harvested organic phosphorus mass | kg P/ha |

The average-annual writer divides each plant's accumulated `organic_mass` yield record by its harvest count when positive, then writes its four components `m`, `c`, `n`, and `p`. The dates are the final simulation date.

{% hint style="warning" %}
The source opens and prints the yearly HRU TXT/CSV headers for `crop_yld = y` or `b`, but no data-row write to units 4010 or 4011 is present in the inspected source. The average-annual TXT/CSV files are opened for `a` or `b` and do have end-of-simulation data writes.
{% endhint %}

The average-annual CSV header is shorter: `jday`, `mon`, `day`, `year`, `unit`, `plantnm`, and `yield`. Its data write passes the same four-component `yield_tot` record as the TXT writer. The TXT and CSV headings are therefore not interchangeable, and the CSV header does not name the carbon, nitrogen, and phosphorus components.

[HRU file creation and headings](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_init.f90#L1252), [average-annual write](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_output.f90#L306), [yield record fields](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/organic_mineral_mass_module.f90#L7)

[Back to the Plant and Weather index](README.md).
