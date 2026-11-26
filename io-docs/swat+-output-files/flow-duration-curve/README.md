# Flow Duration Curve

`flow_duration_curve.out` summarizes the daily outflow of each SWAT-DEG channel at simulation end. At source revision `6f515368`, each reported exceedance value is the median of the corresponding annual ranked values.

## How to produce this file

Set `fdcout` to `y` in the `crop_yld mgtout hydcon fdcout` settings line of [print.prt](../../introduction-1/simulation-settings/print.prt/README.md). It is the fourth value on that line. SWAT+ computes curves for SWAT-DEG channel objects (`chandeg`) and writes the TXT summary to `flow_duration_curve.out` at the end of the run. [Settings reader](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_print_codes_read.f90#L39), [File creation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_write.f90#L15), [Channel filter](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L412), [Summary writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/flow_dur_curve.f90#L145)

| Field | Description | Unit |
| --- | --- | --- |
| [ob_typ](ob_typ.md) | Object type | n/a |
| [props](props.md) | Property reference from channel connectivity | n/a |
| [area_ha](area_ha.md) | Object area from channel connectivity | ha |
| [flash_idx](flash_idx.md) | Ratio of summed signed daily flow changes to summed daily flow before the final day | n/a |
| [mean](mean.md) | Reported mean-flow statistic; see calculation caveat below | m3/s |
| [max](max.md) | Maximum flow | m3/s |
| [p.1](p-dot-1.md) | Flow at nominal .1% exceedance, aggregated from annual curves | m3/s |
| [p.5](p-dot-5.md) | Flow at nominal .5% exceedance, aggregated from annual curves | m3/s |
| [p1](p1.md) | Flow at nominal 1% exceedance, aggregated from annual curves | m3/s |
| [p2](p2.md) | Flow at nominal 2% exceedance, aggregated from annual curves | m3/s |
| [p3](p3.md) | Flow at nominal 3% exceedance, aggregated from annual curves | m3/s |
| [p5](p5.md) | Flow at nominal 5% exceedance, aggregated from annual curves | m3/s |
| [p10](p10.md) | Flow at nominal 10% exceedance, aggregated from annual curves | m3/s |
| [p15](p15.md) | Flow at nominal 15% exceedance, aggregated from annual curves | m3/s |
| [p20](p20.md) | Flow at nominal 20% exceedance, aggregated from annual curves | m3/s |
| [p25](p25.md) | Flow at nominal 25% exceedance, aggregated from annual curves | m3/s |
| [p30](p30.md) | Flow at nominal 30% exceedance, aggregated from annual curves | m3/s |
| [p35](p35.md) | Flow at nominal 35% exceedance, aggregated from annual curves | m3/s |
| [p40](p40.md) | Flow at nominal 40% exceedance, aggregated from annual curves | m3/s |
| [p45](p45.md) | Flow at nominal 45% exceedance, aggregated from annual curves | m3/s |
| [p50](p50.md) | Flow at nominal 50% exceedance, aggregated from annual curves | m3/s |
| [p55](p55.md) | Flow at nominal 55% exceedance, aggregated from annual curves | m3/s |
| [p60](p60.md) | Flow at nominal 60% exceedance, aggregated from annual curves | m3/s |
| [p65](p65.md) | Flow at nominal 65% exceedance, aggregated from annual curves | m3/s |
| [p70](p70.md) | Flow at nominal 70% exceedance, aggregated from annual curves | m3/s |
| [p75](p75.md) | Flow at nominal 75% exceedance, aggregated from annual curves | m3/s |
| [p80](p80.md) | Flow at nominal 80% exceedance, aggregated from annual curves | m3/s |
| [p85](p85.md) | Flow at nominal 85% exceedance, aggregated from annual curves | m3/s |
| [p90](p90.md) | Flow at nominal 90% exceedance, aggregated from annual curves | m3/s |
| [p95](p95.md) | Flow at nominal 95% exceedance, aggregated from annual curves | m3/s |
| [p97](p97.md) | Flow at nominal 97% exceedance, aggregated from annual curves | m3/s |
| [p98](p98.md) | Flow at nominal 98% exceedance, aggregated from annual curves | m3/s |
| [p99](p99.md) | Flow at nominal 99% exceedance, aggregated from annual curves | m3/s |
| [min](min.md) | Minimum flow | m3/s |

The file writes a simulation identification line, 34 headings, and 34 data values per channel, with no units row. The headings include `p.1` and `p.5`. The writer takes the daily total outflow volume from `ob(icmd)%hd(1)%flo` after channel processing, including the pass-through path for near-zero-length channels. Collection starts in the first simulation year and includes the `nyskip` warm-up years. Flow statistics are converted from daily m³ to m³/s by dividing by 86,400. [Channel dispatch and collection](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L375-L425), [conversion and write](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/flow_dur_curve.f90#L133-L146).

## Partial years and fixed ranks

The final simulated day enters the annual ranking before the end-of-run summary is written, even when that day falls midmonth or midyear. The writer ranks flows from highest to lowest using the same 27 positions in every year. It takes the median across years for each position, averaging the two middle values when the year count is even. [Calendar flags](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_control.f90#L138-L143) · [Year and simulation end](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_control.f90#L180-L188) · [Daily insertion and annual ranking](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/flow_dur_curve.f90#L19-L74) · [Across-year median](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/flow_dur_curve.f90#L75-L129)

For a 100-day year starting January 1, `p25` still takes the 91st-highest daily flow and `p50` still requests rank 182. The unavailable annual `p50` keeps its initial zero and enters the median. In a two-year run with a first-year `p50` of 20 m³/s and a 100-day final year, the reported `p50` is 10 m³/s. A first year that starts after January 1 can encounter invalid linked-list indices because the routine counts by day of year from 1. [Rank constants and zero default](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L298-L308) · [Annual ranking and list traversal](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/flow_dur_curve.f90#L19-L70)

{% hint style="warning" %}
The annual `mean` uses an N+1 divisor after summing N day slots. The printed statistic gives each annual result equal weight, including a partial year. The `flash_idx` calculation uses signed differences, so rises and falls cancel. It also excludes the final day from both sums because the writer runs before that day's flashiness update. [Mean calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/flow_dur_curve.f90#L58-L62), [flashiness call order](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L412-L419).
{% endhint %}
