# Channel

Use the file-family index below to find the printed schema for each channel report. In [print.prt](../../introduction-1/simulation-settings/print.prt/README.md), select daily, monthly, yearly, or average-annual periods on `channel_sd` for per-channel SWAT-DEG output and `basin_sd_cha` for basin output. Set `csvout = y` for CSV variants where the source provides them.

| File family | Schema |
| --- | --- |
| `channel_sd_*` | [SD channel general output](sd-channel-general.md), 66 columns |
| `basin_sd_cha_*` | [Basin SD channel general output](basin-sd-channel-general.md), 65 columns |
| `channel_sdmorph_*`, `basin_sd_chamorph_*` | [SD channel morphology output](sd-channel-morphology.md), 33 columns |
| `channel_*`, `basin_cha_*` | [Alternate channel routing output](alternate-channel-routing.md), 66 columns |
| `channel_sd_subday.txt` | [Subdaily SD channel flow](subdaily-sd-channel-flow.md), nine-column TXT data layout with CSV/header limitations |

The alternate routing openers read `channel` and `basin_cha` rather than the SWAT-DEG rows. See the [alternate routing page](alternate-channel-routing.md) for the disabled routing branch and file availability. [Basin print row](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_print_codes_read.f90#L223), [Individual print row](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_print_codes_read.f90#L537)
