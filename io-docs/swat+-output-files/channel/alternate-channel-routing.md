# Alternate Channel Routing Output

The alternate `channel_*` and `basin_cha_*` reports have 66 columns in the source. In [print.prt](../../introduction-1/simulation-settings/print.prt/README.md), their openers read `channel` and `basin_cha`, respectively. The four period columns select daily, monthly, yearly, and average annual. `csvout = y` adds CSV files. The individual opener requires alternate channel objects. The basin opener can create headers from the print setting alone. [Print row names](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_print_codes_read.f90#L537), [Individual opener](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_channel.f90#L24), [Basin opener](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_write.f90#L246)

{% hint style="warning" %}
At source revision `6f515368`, the `chan` routing branch is commented out. The output writers remain in the source, but this review found no active calculation that populates their daily `ch_d` record. The table describes the file layout defined by those writers. [Routing branch](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L305), [Writer calls](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L574)
{% endhint %}

Both alternate writers transfer monthly accumulators only at calendar month end. Their yearly and average-annual accumulation paths omit a final partial month. [Individual period logic](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/channel_output.f90#L37-L65), [basin period logic](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_channel_output.f90#L33-L62).

The basin writer places `1` in both identifier columns and writes the basin name. Its operator adds records across channels and over time, including concentration fields. The operator leaves `ch_dep` at its default zero during addition and division. The daily and monthly basin CSV files have their own filenames, but the output registry lists their TXT names a second time. [Basin writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_channel_output.f90#L12), [Addition and division](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/channel_module.f90#L356), [Registry entries](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_write.f90#L253)

The table uses physical or declared units where identified. The printed units row gives `----` for the fields from `bacp` to `tot_ssed`. For `evap` and `tloss`, it prints `ha-m` while the record comments say `m3/s`. The inactive routing branch leaves that conflict unresolved. [Record declarations](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/channel_module.f90#L122), [Printed units](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/channel_module.f90#L272)

| Field | Description | Unit |
| --- | --- | --- |
| [jday](jday-alternate-channel-routing-output.md) | Day of year | n/a |
| [mon](mon-alternate-channel-routing-output.md) | Month | n/a |
| [day](day-alternate-channel-routing-output.md) | Day of month | n/a |
| [yr](yr-alternate-channel-routing-output.md) | Calendar year | n/a |
| [unit](unit-alternate-channel-routing-output.md) | Object identifier | n/a |
| [gis_id](gis_id-alternate-channel-routing-output.md) | GIS identifier | n/a |
| [name](name-alternate-channel-routing-output.md) | Object name | n/a |
| [flo_in](flo_in-alternate-channel-routing-output.md) | Incoming water volume | ha-m |
| [flo_out](flo_out-alternate-channel-routing-output.md) | Outgoing water volume | ha-m |
| [evap](evap-alternate-channel-routing-output.md) | Evaporation loss | ha-m |
| [tloss](tloss.md) | Transmission loss | ha-m |
| [sed_in](sed_in-alternate-channel-routing-output.md) | Incoming sediment | tons |
| [sed_out](sed_out-alternate-channel-routing-output.md) | Outgoing sediment | tons |
| [sed_conc](sed_conc.md) | Sediment concentration | mg/L |
| [orgn_in](orgn_in-alternate-channel-routing-output.md) | Incoming organic nitrogen | kg N |
| [orgn_out](orgn_out-alternate-channel-routing-output.md) | Outgoing organic nitrogen | kg N |
| [orgp_in](orgp_in.md) | Incoming organic phosphorus | kg P |
| [orgp_out](orgp_out.md) | Outgoing organic phosphorus | kg P |
| [no3_in](no3_in-alternate-channel-routing-output.md) | Incoming nitrate nitrogen | kg N |
| [no3_out](no3_out-alternate-channel-routing-output.md) | Outgoing nitrate nitrogen | kg N |
| [nh4_in](nh4_in.md) | Incoming ammonium | kg |
| [nh4_out](nh4_out.md) | Outgoing ammonium | kg |
| [no2_in](no2_in-alternate-channel-routing-output.md) | Incoming nitrite | kg |
| [no2_out](no2_out-alternate-channel-routing-output.md) | Outgoing nitrite | kg |
| [solp_in](solp_in-alternate-channel-routing-output.md) | Incoming soluble phosphorus | kg P |
| [solp_out](solp_out-alternate-channel-routing-output.md) | Outgoing soluble phosphorus | kg P |
| [chla_in](chla_in-alternate-channel-routing-output.md) | Incoming chlorophyll a | kg |
| [chla_out](chla_out-alternate-channel-routing-output.md) | Outgoing chlorophyll a | kg |
| [cbod_in](cbod_in-alternate-channel-routing-output.md) | Incoming carbonaceous biochemical oxygen demand | kg |
| [cbod_out](cbod_out-alternate-channel-routing-output.md) | Outgoing carbonaceous biochemical oxygen demand | kg |
| [dis_in](dis_in.md) | Incoming dissolved oxygen | kg |
| [dis_out](dis_out.md) | Outgoing dissolved oxygen | kg |
| [solpst_in](solpst_in.md) | Incoming dissolved pesticide | mg |
| [solpst_out](solpst_out.md) | Outgoing dissolved pesticide | mg |
| [sorbpst_in](sorbpst_in.md) | Incoming sorbed pesticide | mg |
| [sorbpst_out](sorbpst_out.md) | Outgoing sorbed pesticide | mg |
| [react](react.md) | Pesticide reaction loss in water | mg |
| [volat](volat.md) | Pesticide volatilization | mg |
| [setlpst](setlpst.md) | Pesticide settling | mg |
| [resuspst](resuspst.md) | Pesticide resuspension | mg |
| [difus](difus.md) | Pesticide diffusion | mg |
| [reactb](reactb.md) | Pesticide reaction loss in benthic sediment | mg |
| [bury](bury.md) | Pesticide burial | mg |
| [sedpest](sedpest.md) | Pesticide in sediment | mg |
| [bacp](bacp.md) | Persistent bacteria output | model count |
| [baclp](baclp.md) | Less-persistent bacteria output | model count |
| [met1](met1.md) | Metal 1 output | constituent-dependent |
| [met2](met2.md) | Metal 2 output | constituent-dependent |
| [met3](met3.md) | Metal 3 output | constituent-dependent |
| [sand_in](sand_in.md) | Incoming sand | tons |
| [sand_out](sand_out.md) | Outgoing sand | tons |
| [silt_in](silt_in.md) | Incoming silt | tons |
| [silt_out](silt_out.md) | Outgoing silt | tons |
| [clay_in](clay_in.md) | Incoming clay | tons |
| [clay_out](clay_out.md) | Outgoing clay | tons |
| [smag_in](smag_in.md) | Incoming small aggregates | tons |
| [smag_out](smag_out.md) | Outgoing small aggregates | tons |
| [lag_in](lag_in-alternate-channel-routing-output.md) | Incoming large aggregates | tons |
| [lag_out](lag_out-alternate-channel-routing-output.md) | Outgoing large aggregates | tons |
| [grvl_in](grvl_in.md) | Incoming gravel | tons |
| [grvl_out](grvl_out.md) | Outgoing gravel | tons |
| [bnk_ero](bnk_ero.md) | Bank erosion | tons |
| [ch_deg](ch_deg.md) | Channel degradation | tons |
| [ch_dep](ch_dep.md) | Channel deposition | tons |
| [fp_dep](fp_dep.md) | Floodplain deposition | tons |
| [tot_ssed](tot_ssed.md) | Total suspended sediment concentration | mg/L |

[Back to the Channel index](README.md).
