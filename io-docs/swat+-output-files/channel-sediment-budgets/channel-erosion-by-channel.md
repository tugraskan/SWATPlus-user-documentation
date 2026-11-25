# Channel Erosion by Channel

`ch_sedbud_*` writes one row per SWAT-DEG channel at the requested interval. The `_d`, `_m`, `_y`, and `_a` suffixes select daily, monthly, yearly, and average-annual files in TXT and optional CSV. [File creation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_sd_channel.f90#L349), [Writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_sedbud_output.f90#L12-L101)

{% hint style="warning" %}
On SWAT+ dev each row has **17 values but the heading line has 16 names**. The writer prints `ob_days` after `fp_km2`, and the header has no name for it ([headings](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L532-L570)). From position 11 on, each heading sits one column to the left of its value, and the last value (`fp_mm`) has no heading. Read the columns by the order in the table below.
{% endhint %}

| Position | Field | Description | Unit |
| ---: | --- | --- | --- |
| 1 | `jday` | Day of year | n/a |
| 2 | `mon` | Month | n/a |
| 3 | `day` | Day of month | n/a |
| 4 | `yr` | Calendar year | n/a |
| 5 | `ichan` | Index within the SWAT-DEG channel list | n/a |
| 6 | `ob` | Channel object's GIS ID | n/a |
| 7 | `name` | Channel object name | n/a |
| 8 | `wid` | Channel width when the row is written | m |
| 9 | `dep` | Channel depth when the row is written | m |
| 10 | `fp_km2` | Floodplain area estimate (5 × width × length) when the row is written | km² |
| 11 | `ob_days` (no heading) | Days with overbank flow | days |
| 12 | `ebank_t` | Bank erosion mass | tons |
| 13 | `ebtm_t` | Bed erosion mass | tons |
| 14 | `ebank_m` | Bank cutting distance | m |
| 15 | `ebtm_m` | Bed cutting depth | m |
| 16 | `fp_t` | Floodplain sediment deposited | tons |
| 17 | `fp_mm` | Floodplain deposition thickness | mm |

Positions 8–10 are the channel's current geometry (`sd_ch(ichan)%chw`, `%chd`, `%fp_km2`), not accumulated values; in monthly, yearly and average-annual rows they are the values on the day the row is written ([`ch_sedbud_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_sedbud_output.f90#L20-L26)). The floodplain area is recomputed each day the channel has inflow ([`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L300-L304)).

The simulation clears the per-channel records at the start of each day ([daily reset](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_control.f90#L241-L245)). A channel adds to them only when its inflow is above `1.e-6` m³ ([inflow gate](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L81-L82)); the near-zero-length channel bypass skips the calculation ([channel bypass](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L375-L408)). Reporting starts after `nyskip` ([report calls](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L441-L450)).

`ob_days` counts days on which the overbank fraction of flow exceeds 0.05 ([`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L137-L140)). `fp_mm` spreads the deposited mass over the floodplain area, with an assumed bulk density of 1 t/m³ ([`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L300-L304)).

## Erosion and deposition calculations

- **Values used by the daily routine.** On SWAT+ dev the routine no longer replaces `bankfull_flo`, `fp_inun_days`, `d50` and `bed_exp` with fixed values; the inputs are used ([`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L75-L79)).
- **Floodplain deposition (dev).** The fraction of flow that goes overbank is `0.8 · q³ / (q³ + q_bf³)`, where `q` is the peak rate and `q_bf` is `bankfull_flo` times the second rating-curve flow. When it exceeds 0.05, the trap efficiency is `1 − exp(−A_fp / V_ob)` with floodplain area `A_fp = 5 × width × length` and overbank volume `V_ob`, and the deposited sediment, organic N and organic P are trap efficiency × overbank fraction × the inflow amounts (N and P also times their enrichment ratios) ([`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L108-L162)).
{% hint style="info" %}
The bank- and bed-erosion notes below were checked on SWAT+ main (`6f515368`) and have not yet been rechecked on dev.
{% endhint %}

- **Bank erosion.** Bank cutting begins when the bend-adjusted velocity exceeds the critical velocity. The active mass calculation uses the computed cutting distance, channel depth, bulk density, and one quarter of the channel length. The routine computes a protected length using `arc_len_fr`, but the active mass expression uses the quarter-length directly. [Bank calculation](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/sd_channel_sediment3.f90#L168-L215).
- **Bed erosion.** Bed cutting requires slope above `1.e-6` and velocity above `0.293 * sqrt(d50)`. The routine writes gross bed erosion mass to `ebtm_t` here and in the stream-order summary. The [nutrient and sediment budget](channel-nutrient-sediment-budget.md) writes `bed_ero` after multiplying that gross mass by `wash_bed_fr`. The line that would add the calculated bed load to the routed hydrograph is commented out. [Bed calculation and reporting](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/sd_channel_sediment3.f90#L248-L296), [budget assignment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_control3.f90#L414-L421).

Monthly and yearly rows sum positions 11–17 over the period (including `ob_days`); average-annual rows divide them by the number of printed years ([period accumulation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_sedbud_output.f90#L15-L101), [addition and division](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L696-L721)).

If the run ends before the last day of the month, the yearly accumulator includes the remaining monthly values. That partial month has no separate monthly row. The [stream-order writer](channel-erosion-by-order.md) follows the same rule. [Month and year writes](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/ch_sedbud_output.f90#L33-L73).

[Back to the Channel Sediment Budgets index](README.md).
