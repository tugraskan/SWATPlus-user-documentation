# Water Allocation

This page describes SWAT+ dev `aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715`. Use the file-family index below to find the printed record structure and file-specific warnings. Daily, monthly, yearly, and average-annual files use `_day`, `_mon`, `_yr`, and `_aa` suffixes and have TXT and optional CSV variants.

## How to produce these files

Configure [place_of_use.wro](../../introduction-1/water-allocation/place_of_use.wro/README.md) and [point_of_diver.wro](../../introduction-1/water-allocation/point_of_diver.wro/README.md) using the filenames on the water-allocation row of `file.cio`. These are the default filenames on this revision. [Default filenames](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/input_file_module.f90#L145-L146), [Allocation input reader](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L39-L42)

In [print.prt](../../introduction-1/simulation-settings/print.prt/README.md), set the daily, monthly, yearly, or average-annual columns of `water_allo` to `y`. For example, `water_allo y n n n` enables the daily files. Set `csvout` to `y` to also request CSV. The schema pages record file-specific CSV limitations. The writers run only after the skipped years. [Print row](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_print_codes_read.f90#L311-L317), [File creation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_water_allocation.f90#L10-L194), [Reporting gate and callers](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L441-L458)

| File family | Schema |
| --- | --- |
| `wallo_met_*` | [Allocation transactions](allocation-transactions.md#pou-totals): duty and delivery per place of use (POU) |
| `wallo_pou_pods_*` | [Allocation transactions](allocation-transactions.md#pou-pod-rows): duty, withdrawal and withdrawn hydrograph per point of diversion (POD) |
| `wallo_pou_pors_*` | [Allocation transactions](allocation-transactions.md#pou-por-rows): hydrograph sent to each receiving point (POR) |
| `wallo_use_*` | [Water-use diagnostics](water-use.md) |
| `wallo_treat_*` | [Water-treatment diagnostics](water-treatment.md) |

{% hint style="info" %}
SWAT+ main wrote all transactions to one interleaved `water_allo_*` file family. Dev replaces it with the three `wallo_met_*`, `wallo_pou_pods_*` and `wallo_pou_pors_*` families; the `water_allo` print row is unchanged.
{% endhint %}
