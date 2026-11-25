# Wetland constituent output

The `wetland_cs_day`, `wetland_cs_mon`, `wetland_cs_yr`, and `wetland_cs_aa` files are available as TXT and CSV. Enable the desired periods on `res_cs` in [print.prt](../../introduction-1/simulation-settings/print.prt/README.md) and set `csvout` to `y` for CSV copies. In this source revision, the file opener requires at least one reservoir object and one configured conservative constituent. A data row comes from a full HRU with a wetland assignment. The daily writer runs after the skipped years and uses the daily switch without a separate day window or interval. [File creation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L880), [Output caller](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L440), [Wetland writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_cs_output.f90#L40)

{% hint style="warning" %}
The wetland writer skips the diversion group in every period and both formats. With three configured constituents, it writes 37 values under 40 headings. Read by position from column 31 onward. The final three headings have no corresponding row values.
{% endhint %}

## Column order

The first six headings are `jday`, `mon`, `day`, `yr`, `unit`, and `gis_id`. The table maps the remaining printed headings to the values written at those positions when the configured constituent count is three. The data groups expand with the configured count while the headings stay fixed. [Header declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_cs_module.f90#L57), [Data write](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_cs_output.f90#L43)

| Columns | Printed headings | Actual values | Unit |
| --- | --- | --- | --- |
| 7–9 | `seo4_in`, `seo3_in`, `born_in` | Mass entering with inflow | kg |
| 10–12 | `seo4_out`, `seo3_out`, `born_out` | Mass leaving with outflow | kg |
| 13–15 | `seo4_seep`, `seo3_seep`, `born_seep` | Mass leaving by seepage | kg |
| 16–18 | `seo4_setl`, `seo3_setl`, `born_setl` | Mass settling to the bottom | kg |
| 19–21 | `seo4_rctn`, `seo3_rctn`, `born_rctn` | Mass consumed by chemical reactions | kg |
| 22–24 | `seo4_prod`, `seo3_prod`, `born_prod` | Mass produced by chemical reactions | kg |
| 25–27 | `seo4_fert`, `seo3_fert`, `born_fert` | Mass added by fertilizer | kg |
| 28–30 | `seo4_irrg`, `seo3_irrg`, `born_irrg` | Mass added by irrigation | kg |
| 31–33 | `seo4_div`, `seo3_div`, `born_div` | Stored constituent mass | kg |
| 34–36 | `seo4_mass`, `seo3_mass`, `born_mass` | Concentration in stored water | g/m3 |
| 37 | `seo4_conc` | Stored water volume | m3 |
| 38–40 | `seo3_conc`, `born_conc`, `vol_m3` | No row values | — |

## Reporting periods

Daily rows report the values from the wetland constituent calculation. Monthly and yearly rows sum the mass transfers and divide the daily sums of stored mass, concentration, and volume by the calendar month length or `time%day_end_yr`, respectively. Average-annual rows divide all daily sums by the configured number of simulation years (`time%nbyr`). The three storage groups in those rows therefore represent sums of daily values per configured year. Mass transfers are reported in kg/yr for average annual output. [Period calculations](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_cs_output.f90#L74)

The writer transfers monthly sums into the yearly record only at calendar month end. If the simulation ends midmonth, the yearly and average-annual sums omit that final partial month. Any yearly state means still use `time%day_end_yr` as the divisor. [Month-end transfer and year-end processing](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_cs_output.f90#L73-L139)

## Where the daily values come from

The wetland calculation runs after water seepage and release. It divides the stored constituent mass by the remaining water volume to calculate the starting concentration, then adds constituent mass from the surface-runon hydrograph to the amount available. It calculates and caps outflow, seepage, settling, and reaction losses in that order. Selenate lost by reaction becomes an equal mass of selenite production. The routine records the remaining mass and its concentration after the constituent balance, despite the beginning-of-day wording in the TXT preamble. [Release and constituent call](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wetland_control.f90#L176-L225) · [Mass calculation and assignments](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_cs.f90#L54-L149) · [TXT preamble](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L899-L901)

The daily outflow and seepage masses are divided by HRU area. Outflow contributes to the [HRU wetland-runoff diagnostic](hru.md#where-the-daily-values-come-from), and seepage mass is added to the top soil layer. The wetland constituent calculation uses the water-budget seepage volume, including when the water volume comes from the GWFlow path. [Transfer to the HRU](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_cs.f90#L151-L157) · [Water-seepage path](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wetland_control.f90#L99-L105) · [GWFlow seepage volume](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_wetland.f90#L139-L146)

At a remaining volume of 1 m³ or less, the constituent routine skips the mass balance. It clears the reported mass and concentration on entry, but the volume slot can retain its earlier value. The writer puts this volume under the `seo4_conc` heading. [Entry resets and volume gate](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_cs.f90#L41-L57) · [Volume assignment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_cs.f90#L140-L150) · [Basin reset list](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_balance.f90#L613-L622)

The standing-water fertilizer operation adds each application to stored constituent mass but replaces the fertilizer diagnostic, so several applications can be represented by only the last one in the table. Irrigation assignments in `cs_irrig` and `gwflow_pump_allo` have no active callers in the inspected source, and the constituent routine clears irrigation on entry. [Standing-water operation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L375-L384) · [Fertilizer assignments](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_fert_wet.f90#L27-L40) · [Disabled allocation call](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/wallo_pou_deliv.f90#L61-L68) · [GWFlow irrigation assignment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_pump_allo.f90#L141-L151) · [Entry resets](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_cs.f90#L41-L52)

[Back to the Conservative Constituents index](README.md).
