# Basin Recall Sum

`basin_psc_day`, `basin_psc_mon`, `basin_psc_yr`, and `basin_psc_aa` each have TXT and optional CSV variants. Every data row has 23 values: `jday`, `mon`, `day`, `yr`, basin `name`, then the same 18 hydrograph components from [flo](flo.md) through numeric [null](null.md). There is no `type` data value. [Basin summation and writers](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_recall_output.f90#L10)

The daily record is a basin sum of all `rec_d(irec)` hydrographs, not an average across recall objects. Daily values accumulate into monthly and yearly totals. Average annual divides the accumulated volume and mass components by `time%yrs_prt`, while the hydrograph division operator leaves temperature unchanged.

The basin writer sums the same daily records used by the individual outputs. It therefore includes the repeated daily values from monthly and yearly inputs. Negative-volume diversions contribute signed volume to the sum, and the calculated channel nutrient removals stay outside the Recall mass columns. [Input time basis and diversions](individual-recall.md#how-recall-inputs-become-daily-output).

The basin writer transfers monthly values at calendar month end. The yearly and average-annual sums omit a final partial month. [Basin period accumulation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_recall_output.f90#L30-L59).

| Position | Field | Meaning | Unit |
| ---: | --- | --- | --- |
| 1–4 | `jday`, `mon`, `day`, `yr` | Reporting date | n/a |
| 5 | `name` | Basin name | n/a |
| 6–23 | `flo` … `null` | Shared 18-value hydrograph payload | See the linked field pages |

{% hint style="warning" %}
The basin header uses the six-entry `rec_hdr_time`, whose sixth entry is blank, followed by the 18 hydrograph headings. TXT and CSV headers therefore contain 24 entries, while every basin data row contains 23 values and has no value for that blank position. Unlike the individual Recall CSVs, the basin CSV units row uses the full 24-entry `hyd_hdr_units`: six blank identifier units followed by 18 component units. It is aligned with the 24-entry heading row—including the empty sixth heading—but remains one entry wider than the 23-value data row. Its flow label is `m^3/s`; the writer emits the summed volume without a rate conversion, so the field page uses m3.
{% endhint %}

[Back to the Recall index](README.md).
