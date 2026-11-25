# GWFlow Channel Separation

`gwflow_chan_hydsep_day.txt` has a fixed 14-column header. The first seven fields are `jday`, `mon`, `day`, `yr`, `unit` (the SD channel index), `gis_id`, and `name`. The units row labels all seven remaining positions m³/s. [Header and units](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L2350-L2364), [daily writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L657-L668).

## How to produce this file

Enable GWFlow and set the daily column of `gwflow_wb` to `y` in `print.prt`. If the `gwflow_wb` row is absent, the writer uses `write_day` from `codes.gw`. It writes one row per SD channel (`chandeg`) per day, including warm-up days skipped by the general `print.prt` `nyskip` setting. The GWFlow heat switch does not control this report or the temperature overwrite. [Print override](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L253-L271), [daily file and channel flags](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L2349-L2364), [command output order](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L641-L668).

## Values actually written

{% hint style="warning" %}
For SD channels that enter the normal controller, `ch_temp` replaces all seven fields before the daily writer reads them. The resulting row includes HRU water depths and temperatures under flow headings. Channels that always take the short-channel bypass (`chl <= 0.001` km) still get rows with seven zeros because the shared array starts at zero and the bypass leaves it untouched.
{% endhint %}

| Printed heading | Routed component before overwrite | Value written for a normally routed channel | Actual unit |
| --- | --- | --- | --- |
| `surf_runoff` | `hdsep2%flo_surq` | `q_ru_surf`, sum of HRU `surq_gen` | mm |
| `lateral` | `hdsep2%flo_latq` | `q_ru_lat`, sum of HRU `latq` | mm |
| `gw_discharge` | `hdsep2%flo_gwsw` | `q_gw`, incoming `hdsep1%flo_gwsw / 86400` capped at 10 m³/s | m³/s |
| `stream_seep` | `hdsep2%flo_swgw` | `q_ru_wyld`, sum of HRU `wateryld`, with `1e-6` substituted when the sum is zero | mm |
| `satex_gw` | `hdsep2%flo_satex` | `q_ru_sno`, sum of HRU `snomlt` multiplied by each routing-unit element's fraction | mm |
| `satex_sw` | `hdsep2%flo_satexsw` | `tw_final`, stream temperature after heat exchange, with a minimum of `0.001` | °C |
| `tile_drain` | `hdsep2%flo_tile` | `tw_init`, mixed stream temperature before heat exchange | °C |

The controller divides the routed volumes in the second column by 86,400 before storing them in the shared array. `q_gw` uses the incoming separation record, which is copied before the local GWFlow exchanges run. [Controller sequence](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_control3.f90#L314-L357), [incoming separation record](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_control3.f90#L96-L151), [groundwater cap](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_temp.f90#L232-L242).

`ch_temp` builds the HRU sums from incoming routing units without converting depths to volumes. Only the snowmelt sum uses the element fraction. The code tests for an HRU using the loop position in the global element array, then looks up the values using the routing unit's element index. When those indices differ, the test can check a different element from the one used in the sum. [HRU lookups and sums](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_temp.f90#L207-L232), [HRU units](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L8-L11).

[Initial temperature](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_temp.f90#L347-L355), [final temperature and overwrite](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_temp.f90#L438-L461), [zero initialization](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_read.f90#L92-L96), [short-channel bypass](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L374-L402).

[Back to the GWFlow Outputs index](README.md).
