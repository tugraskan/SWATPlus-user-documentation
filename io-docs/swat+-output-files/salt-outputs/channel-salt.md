# Channel salt

Configure salts, then select the desired periods on `channel_salt` in [print.prt](../../introduction-1/simulation-settings/print.prt/README.md). This report requires an SD channel object (`sp_ob%chandeg`). Set `csvout` to `y` for CSV copies. Daily output uses the daily switch after skipped years without a separate day window or interval. [File opener](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_salt.f90#L464), [Output caller](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L579), [Daily writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_salt_output.f90#L40)

## Column order

The first six headings are `jday`, `mon`, `day`, `yr`, `unit`, and `gis_id`. The fixed header has 70 columns. The data writer emits one value per configured salt ion in each of the eight groups, giving 70 row values with eight ions. [Header declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_salt_module.f90#L28), [Data write](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_salt_output.f90#L42)

| Field | Description | Unit |
| --- | --- | --- |
| [`so4_in`](so4_in.md) | Reported total sulfate inlet, including groundwater from the linked aquifer | kg |
| [`ca_in`](ca_in.md) | Reported total calcium inlet, including groundwater from the linked aquifer | kg |
| [`mg_in`](mg_in.md) | Reported total magnesium inlet, including groundwater from the linked aquifer | kg |
| [`na_in`](na_in.md) | Reported total sodium inlet, including groundwater from the linked aquifer | kg |
| [`k_in`](k_in.md) | Reported total potassium inlet, including groundwater from the linked aquifer | kg |
| [`cl_in`](cl_in.md) | Reported total chloride inlet, including groundwater from the linked aquifer | kg |
| [`co3_in`](co3_in.md) | Reported total carbonate inlet, including groundwater from the linked aquifer | kg |
| [`hco3_in`](hco3_in.md) | Reported total bicarbonate inlet, including groundwater from the linked aquifer | kg |
| [`so4_gw`](so4_gw.md) | Sulfate from groundwater via the linked-aquifer diagnostic | kg |
| [`ca_gw`](ca_gw.md) | Calcium from groundwater via the linked-aquifer diagnostic | kg |
| [`mg_gw`](mg_gw.md) | Magnesium from groundwater via the linked-aquifer diagnostic | kg |
| [`na_gw`](na_gw.md) | Sodium from groundwater via the linked-aquifer diagnostic | kg |
| [`k_gw`](k_gw.md) | Potassium from groundwater via the linked-aquifer diagnostic | kg |
| [`cl_gw`](cl_gw.md) | Chloride from groundwater via the linked-aquifer diagnostic | kg |
| [`co3_gw`](co3_gw.md) | Carbonate from groundwater via the linked-aquifer diagnostic | kg |
| [`hco3_gw`](hco3_gw.md) | Bicarbonate from groundwater via the linked-aquifer diagnostic | kg |
| [`so4_out`](so4_out.md) | Sulfate leaving the channel | kg |
| [`ca_out`](ca_out.md) | Calcium leaving the channel | kg |
| [`mg_out`](mg_out.md) | Magnesium leaving the channel | kg |
| [`na_out`](na_out.md) | Sodium leaving the channel | kg |
| [`k_out`](k_out.md) | Potassium leaving the channel | kg |
| [`cl_out`](cl_out.md) | Chloride leaving the channel | kg |
| [`co3_out`](co3_out.md) | Carbonate leaving the channel | kg |
| [`hco3_out`](hco3_out.md) | Bicarbonate leaving the channel | kg |
| [`so4_seep`](so4_seep.md) | Sulfate lost through channel seepage | kg |
| [`ca_seep`](ca_seep.md) | Calcium lost through channel seepage | kg |
| [`mg_seep`](mg_seep.md) | Magnesium lost through channel seepage | kg |
| [`na_seep`](na_seep.md) | Sodium lost through channel seepage | kg |
| [`k_seep`](k_seep.md) | Potassium lost through channel seepage | kg |
| [`cl_seep`](cl_seep.md) | Chloride lost through channel seepage | kg |
| [`co3_seep`](co3_seep.md) | Carbonate lost through channel seepage | kg |
| [`hco3_seep`](hco3_seep.md) | Bicarbonate lost through channel seepage | kg |
| [`so4_irr`](so4_irr.md) | Sulfate irrigation diagnostic. Zero in the inspected path | kg |
| [`ca_irr`](ca_irr.md) | Calcium irrigation diagnostic. Zero in the inspected path | kg |
| [`mg_irr`](mg_irr.md) | Magnesium irrigation diagnostic. Zero in the inspected path | kg |
| [`na_irr`](na_irr.md) | Sodium irrigation diagnostic. Zero in the inspected path | kg |
| [`k_irr`](k_irr.md) | Potassium irrigation diagnostic. Zero in the inspected path | kg |
| [`cl_irr`](cl_irr.md) | Chloride irrigation diagnostic. Zero in the inspected path | kg |
| [`co3_irr`](co3_irr.md) | Carbonate irrigation diagnostic. Zero in the inspected path | kg |
| [`hco3_irr`](hco3_irr.md) | Bicarbonate irrigation diagnostic. Zero in the inspected path | kg |
| [`so4_div`](so4_div.md) | Last qualifying daily Recall removal of sulfate, recorded as negative | kg |
| [`ca_div`](ca_div.md) | Last qualifying daily Recall removal of calcium, recorded as negative | kg |
| [`mg_div`](mg_div.md) | Last qualifying daily Recall removal of magnesium, recorded as negative | kg |
| [`na_div`](na_div.md) | Last qualifying daily Recall removal of sodium, recorded as negative | kg |
| [`k_div`](k_div.md) | Last qualifying daily Recall removal of potassium, recorded as negative | kg |
| [`cl_div`](cl_div.md) | Last qualifying daily Recall removal of chloride, recorded as negative | kg |
| [`co3_div`](co3_div.md) | Last qualifying daily Recall removal of carbonate, recorded as negative | kg |
| [`hco3_div`](hco3_div.md) | Last qualifying daily Recall removal of bicarbonate, recorded as negative | kg |
| [`so4_mass`](so4_mass.md) | Sulfate stored in channel water | kg |
| [`ca_mass`](ca_mass.md) | Calcium stored in channel water | kg |
| [`mg_mass`](mg_mass.md) | Magnesium stored in channel water | kg |
| [`na_mass`](na_mass.md) | Sodium stored in channel water | kg |
| [`k_mass`](k_mass.md) | Potassium stored in channel water | kg |
| [`cl_mass`](cl_mass.md) | Chloride stored in channel water | kg |
| [`co3_mass`](co3_mass.md) | Carbonate stored in channel water | kg |
| [`hco3_mass`](hco3_mass.md) | Bicarbonate stored in channel water | kg |
| [`so4_conc`](so4_conc.md) | Sulfate concentration in channel outflow | g/m3 |
| [`ca_conc`](ca_conc.md) | Calcium concentration in channel outflow | g/m3 |
| [`mg_conc`](mg_conc.md) | Magnesium concentration in channel outflow | g/m3 |
| [`na_conc`](na_conc.md) | Sodium concentration in channel outflow | g/m3 |
| [`k_conc`](k_conc.md) | Potassium concentration in channel outflow | g/m3 |
| [`cl_conc`](cl_conc.md) | Chloride concentration in channel outflow | g/m3 |
| [`co3_conc`](co3_conc.md) | Carbonate concentration in channel outflow | g/m3 |
| [`hco3_conc`](hco3_conc.md) | Bicarbonate concentration in channel outflow | g/m3 |

## Daily channel calculations

- **Opening storage and inflow.** At startup, the channel multiplies the concentration from its selected `salt_channel.ini` record by initial water volume to get stored mass. The `*_gw` columns report the linked-aquifer share of a saved discharge load. The controller first adds that share to its working inlet, then replaces the working inlet with the original incoming hydrograph. The `*_in` columns still add the linked-aquifer diagnostic to the original load. With GWFlow solutes enabled, channel exchange, tile drainage, saturation excess, and floodplain exchange can change channel salt storage directly. Those changes bypass the linked-aquifer `*_gw` fields. [Opening salt mass](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_hydsed_init.f90#L283-L295), [Linked input and replacement](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_control3.f90#L118-L163), [Printed total input](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_control3.f90#L469-L479), [GWFlow channel exchange](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_channel_exch.f90#L165-L174), [Tile drainage](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_tile.f90#L100-L107), [Saturation excess](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_satexcess.f90#L108-L116), [Floodplain exchange](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_floodplain.f90#L155-L162).
- **Seepage and allocation.** The channel uses incoming salt divided by routed water volume before allocation to calculate the seepage load. It caps that load against the working incoming mass and subtracts it before mixing with storage. With GWFlow enabled, the water router sets this seepage diagnostic's water volume to zero. GWFlow seepage can still change storage directly. The available irrigation salt routine has no active caller, so the `*_irr` fields stay at zero. Channel allocation can reduce outgoing water without taking the corresponding salt out of the routed salt load. [Pre-allocation concentration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_control3.f90#L169-L182), [Seepage cap and subtraction](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_control3.f90#L222-L231), [GWFlow water seepage gate](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_rtmusk.f90#L200-L208), [Inactive salt irrigation call](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/wallo_pou_deliv.f90#L55-L63), [Channel water withdrawal](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/wallo_withdraw.f90#L68-L79).
- **Outflow and storage.** The controller combines the post-seepage load with stored salt, multiplies the mixture by `scoef` for downstream export, and leaves the difference in storage. It updates that coefficient only when travel time exceeds the routing step. Otherwise it can reuse the initialized zero or a value from an earlier call. If inflow is at most `1.e-6` m³, the controller skips formation of the salt mixture and can replace stored salt with zero from the command's cleared scratch record. The salt seepage field is also skipped and can retain an earlier value because the daily salt reset leaves it untouched. The printed concentration divides the resulting salt export by the outgoing water volume after allocation and uses zero at zero outflow. [Mixture and coefficient](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_control3.f90#L263-L292), [Zeroed scratch](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L100-L104), [Outflow and storage assignments](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_control3.f90#L332-L346), [Final concentration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_control3.f90#L469-L479), [Channel daily resets](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_balance.f90#L477-L484).
- **Recall diversions.** A negative daily Recall flow removes salt directly from the first receiving channel's store when the channel has more than 10 m³ stored. The `*_div` field records the last qualifying removal for that day. Positive daily Recall inputs enter the routed inlet and leave the diversion field unchanged. The header describes both signs, but this producer writes removals only. [Recall dispatch](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L339-L356), [Removal and addition paths](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_salt.f90#L26-L51).

## Reporting periods

Yearly and average-annual values omit a final partial month from both flux and state accumulations. The yearly stored mass and concentration still use the final day-of-year divisor. [Month transfer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_salt_output.f90#L65-L81), [year transfer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_salt_output.f90#L119-L135).

Monthly and yearly reports sum mass transfers and divide the daily sums of stored mass and outflow concentration by the calendar month length or `time%day_end_yr`, respectively. This is an arithmetic average of daily concentrations. Average-annual output divides all daily sums by the configured number of simulation years (`time%nbyr`). Stored mass and concentration in those rows represent daily sums per configured year. The average-annual TXT preamble labels mass transfers in kg/yr. [Monthly aggregation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_salt_output.f90#L66), [Yearly aggregation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_salt_output.f90#L119), [Average-annual scaling](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_salt_output.f90#L172)

[Back to the Salt Outputs index](README.md).
