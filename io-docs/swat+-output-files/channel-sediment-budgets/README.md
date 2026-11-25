# Channel Sediment Budgets

Daily, monthly, yearly, and average-annual files use `_day`, `_mon`, `_yr`, and `_aa`. The channel-order and per-channel erosion budgets use `_d`, `_m`, `_y`, and `_a`.

## How to produce these files

In [print.prt](../../introduction-1/simulation-settings/print.prt/README.md), set `channel_sd` to `y` for the desired periods. It controls `sd_chanbud_*`, `ch_sedbud_*`, `chanbud_order_*`, and `sedbud_*`. Use `basin_sd_cha` for `basin_sd_chanbud_*`. The writers require SWAT-DEG channels. Set `csvout` to `y` for CSV variants. [Basin print row](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_print_codes_read.f90#L231), [Channel print row](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_print_codes_read.f90#L545), [Channel budget file creation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_sd_channel.f90#L218), [Basin budget file creation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_write.f90#L433)

| File family | Schema |
| --- | --- |
| `sd_chanbud_*`, `basin_sd_chanbud_*` | [Channel nutrient and sediment budget](channel-nutrient-sediment-budget.md), 37 columns |
| `ch_sedbud_*` | [Channel erosion by channel](channel-erosion-by-channel.md), 17 columns |
| `chanbud_order_*` | [Channel erosion by order](channel-erosion-by-order.md), 15 columns |
| `sedbud_*` | [Basin sediment budget](basin-sediment-budget.md), 10 columns |

The daily nutrient and sediment budgets follow the daily print window and interval. The daily erosion and basin sediment summaries check their daily switch and write on each eligible simulation day after the skipped years. [Reporting calls](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L439), [Nutrient budget daily gate](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_chanbud_output.f90#L16), [Erosion daily gate](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_sedbud_output.f90#L19), [Basin sediment daily gate](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_sedbud_output.f90#L11)
