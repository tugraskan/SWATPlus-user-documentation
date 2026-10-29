# Channel

SWAT+ prints two channel output files per time step, one for general channel output and one for channel morphology output. The printing of channel output is controlled by entering "y" or "n" in the _channel\_sd_ line in [print.prt](../../introduction-1/simulation-settings/print.prt). In addition, a basin average of all channels can be printed by entering "y" in the _basin\_sd\_cha_ line in [print.prt](../../introduction-1/simulation-settings/print.prt). Channel output can be printed at daily, monthly, yearly, and average annual time steps. The names of the channel output files are as follows:&#x20;

* channel\_sd\_day.txt
* channel\_sd\_mon.txt
* channel\_sd\_yr.txt
* channel\_sd\_aa.txt
* channel\_sdmorph\_day.txt
* channel\_sdmorph\_mon.txt
* channel\_sdmorph\_yr.txt
* channel\_sdmorph\_aa.txt
* basin\_sd\_cha\_day.txt
* basin\_sd\_cha\_mon.txt
* basin\_sd\_cha\_yr.txt
* basin\_sd\_cha\_aa.txt
* basin\_sd\_chamorph\_day.txt
* basin\_sd\_chamorph\_mon.txt
* basin\_sd\_chamorph\_yr.txt
* basin\_sd\_chamorph\_aa.txt

{% tabs %}
{% tab title="General" %}
<table><thead><tr><th width="118.66668701171875">Field</th><th width="251.66668701171875">Description</th><th width="99.3333740234375">Unit</th></tr></thead><tbody><tr><td><a href="channel/jday-general.md">jday</a></td><td>Julian Day</td><td>n/a</td></tr><tr><td><a href="channel/mon-general.md">mon</a></td><td>Month</td><td>n/a</td></tr><tr><td><a href="channel/day-general.md">day</a></td><td>Day of the month</td><td>n/a</td></tr><tr><td><a href="channel/yr-general.md">yr</a></td><td>Year</td><td>n/a</td></tr><tr><td><a href="channel/unit-general.md">unit</a></td><td>ID of the object</td><td>n/a</td></tr><tr><td><a href="channel/gis_id-general.md">gis_id</a></td><td>Object ID in GIS</td><td>n/a</td></tr><tr><td><a href="channel/name-general.md">name</a></td><td>Name of the object or SWAT+ setup (basin outputs)</td><td>n/a</td></tr><tr><td><a href="channel/area.md">area</a></td><td>Area of the channel</td><td>ha</td></tr><tr><td><a href="channel/precip.md">precip</a></td><td>Precipitation on the channel surface</td><td>ha-m</td></tr><tr><td><a href="channel/evap-general.md">evap</a></td><td>Evaporation from the channel surface</td><td>ha-m</td></tr><tr><td><a href="channel/seep.md">seep</a></td><td>Seepage out of the channel bottom</td><td>ha-m</td></tr><tr><td><a href="channel/flo_stor.md">flo_stor</a></td><td>Flow storage in the channel</td><td>m3</td></tr><tr><td><a href="channel/sed_stor-general.md">sed_stor</a></td><td>Sediment storage in the channel</td><td>tons</td></tr><tr><td><a href="channel/orgn_stor.md">orgn_stor</a></td><td>Organic nitrogen storage in the channel</td><td>kg</td></tr><tr><td><a href="channel/sedp_stor.md">sedp_stor</a></td><td>Sediment phosphorus storage in the channel</td><td>kg</td></tr><tr><td><a href="channel/no3_stor.md">no3_stor</a></td><td>Nitrate nitrogen storage in the channel</td><td>kg</td></tr><tr><td><a href="channel/solp_stor.md">solp_stor</a></td><td>Soluble phosphorus storage in the channel</td><td>kg</td></tr><tr><td><a href="channel/chla_stor.md">chla_stor</a></td><td>Chlorophyll-a storage in the channel</td><td>kg</td></tr><tr><td><a href="channel/nh3_stor.md">nh3_stor</a></td><td>Ammonia nitrogen storage in the channel</td><td>kg</td></tr><tr><td><a href="channel/no2_stor.md">no2_stor</a></td><td>Nitrite nitrogen storage in the channel</td><td>kg</td></tr><tr><td><a href="channel/cbod_stor.md">cbod_stor</a></td><td>Carbonaceous Biochemical Oxygen Demand storage in the channel</td><td>kg</td></tr><tr><td><a href="channel/dox_stor.md">dox_stor</a></td><td>Dissolved oxygen storage in the channel</td><td>kg</td></tr><tr><td><a href="channel/san_stor.md">san_stor</a></td><td>Sand storage in the channel</td><td>tons</td></tr><tr><td><a href="channel/sil_stor.md">sil_stor</a></td><td>Silt storage in the channel</td><td>tons</td></tr><tr><td><a href="channel/cla_stor.md">cla_stor</a></td><td>Clay storage in the channel</td><td>tons</td></tr><tr><td><a href="channel/sag_stor.md">sag_stor</a></td><td>Small aggregate storage in the channel</td><td>tons</td></tr><tr><td><a href="channel/lag_stor.md">lag_stor</a></td><td>Large aggregate storage in the channel</td><td>tons</td></tr><tr><td><a href="channel/grv_stor.md">grv_stor</a></td><td>Gravel storage in the channel</td><td>tons</td></tr><tr><td><a href="channel/null.md">null</a></td><td></td><td></td></tr><tr><td><a href="channel/flo_in-general.md">flo_in</a></td><td>Flow into the channel</td><td>m3</td></tr><tr><td><a href="channel/sed_in-general.md">sed_in</a></td><td>Sediment entering the channel </td><td>tons</td></tr><tr><td><a href="channel/orgn_in-general.md">orgn_in</a></td><td>Organic nitrogen entering the channel</td><td>kg</td></tr><tr><td><a href="channel/sedp_in.md">sedp_in</a></td><td>Sediment phosphorus entering the channel</td><td>kg</td></tr><tr><td><a href="channel/no3_in-general.md">no3_in</a></td><td>Nitrate nitrogen entering the channel</td><td>kg</td></tr><tr><td><a href="channel/solp_in-general.md">solp_in</a></td><td>Soluble phosphorus entering the channel</td><td>kg</td></tr><tr><td><a href="channel/chla_in-general.md">chla_in</a></td><td>Chlorophyll-a entering the channel </td><td>kg</td></tr><tr><td><a href="channel/nh3_in.md">nh3_in</a></td><td>Ammonia nitrogen entering the channel</td><td>kg</td></tr><tr><td><a href="channel/no2_in-general.md">no2_in</a></td><td>Nitrite nitrogen entering the channel</td><td>kg</td></tr><tr><td><a href="channel/cbod_in-general.md">cbod_in</a></td><td>Carbonaceous Biochemical Oxygen Demand entering the channel</td><td>kg</td></tr><tr><td><a href="channel/dox_in.md">dox_in</a></td><td>Dissolved oxygen entering the channel</td><td>kg</td></tr><tr><td><a href="channel/san_in.md">san_in</a></td><td>Sand entering the channel</td><td>tons</td></tr><tr><td><a href="channel/sil_in.md">sil_in</a></td><td>Silt entering the channel</td><td>tons</td></tr><tr><td><a href="channel/cla_in.md">cla_in</a></td><td>Clay entering the channel</td><td>tons</td></tr><tr><td><a href="channel/sag_in.md">sag_in</a></td><td>Small aggregates entering the channel</td><td>tons</td></tr><tr><td><a href="channel/lag_in-general.md">lag_in</a></td><td>Large aggregates entering the channel</td><td>tons</td></tr><tr><td><a href="channel/grv_in.md">grv_in</a></td><td>Gravel entering the channel</td><td>tons</td></tr><tr><td><a href="channel/null.md">null</a></td><td></td><td></td></tr><tr><td><a href="channel/flo_out-general.md">flo_out</a></td><td>Flow out of the channel</td><td>m3</td></tr><tr><td><a href="channel/sed_out-general.md">sed_out</a></td><td>Sediment leaving the channel</td><td>tons</td></tr><tr><td><a href="channel/orgn_out-general.md">orgn_out</a></td><td>Organic nitrogen leaving the channel</td><td>kg</td></tr><tr><td><a href="channel/sedp_out.md">sedp_out</a></td><td>Sediment phosphorus leaving the channel</td><td>kg</td></tr><tr><td><a href="channel/no3_out-general.md">no3_out</a></td><td>Nitrate nitrogen leaving the channel</td><td>kg</td></tr><tr><td><a href="channel/solp_out-general.md">solp_out</a></td><td>Soluble phosphorus leaving the channel</td><td>kg</td></tr><tr><td><a href="channel/chla_out-general.md">chla_out</a></td><td>Chlorophyll-a leaving the channel</td><td>kg</td></tr><tr><td><a href="channel/nh3_out.md">nh3_out</a></td><td>Ammonia nitrogen leaving the channel</td><td>kg</td></tr><tr><td><a href="channel/no2_out-general.md">no2_out</a></td><td>Nitrite nitrogen leaving the channel</td><td>kg</td></tr><tr><td><a href="channel/cbod_out-general.md">cbod_out</a></td><td>Carbonaceous Biochemical Oxygen Demand leaving the channel</td><td>kg</td></tr><tr><td><a href="channel/dox_out.md">dox_out</a></td><td>Dissolved oxygen leaving the channel</td><td>kg</td></tr><tr><td><a href="channel/san_out.md">san_out</a></td><td>Sand leaving the channel</td><td>tons</td></tr><tr><td><a href="channel/sil_out.md">sil_out</a></td><td>Silt leaving the channel</td><td>tons</td></tr><tr><td><a href="channel/cla_out.md">cla_out</a></td><td>Clay leaving the channel</td><td>tons</td></tr><tr><td><a href="channel/sag_out.md">sag_out</a></td><td>Small aggregates leaving the channel</td><td>tons</td></tr><tr><td><a href="channel/lag_out-general.md">lag_out</a></td><td>Large aggregates leaving the channel</td><td>tons</td></tr><tr><td><a href="channel/grv_out.md">grv_out</a></td><td>Gravel leaving the channel</td><td>tons</td></tr><tr><td><a href="channel/null.md">null</a></td><td></td><td></td></tr></tbody></table>
The current main version appends one additional field after the final `null` separator:

| Field | Description | Unit |
| --- | --- | --- |
| [water_temp](water_temp.md) | Channel water temperature | deg C |

{% endtab %}

{% tab title="Morphology" %}
<table><thead><tr><th width="114.6666259765625">Field</th><th width="250.3333740234375">Description</th><th width="89.333251953125">Unit</th></tr></thead><tbody><tr><td><a href="channel/jday-morphology.md">jday</a></td><td>Julian Day</td><td>n/a</td></tr><tr><td><a href="channel/mon-morphology.md">mon</a></td><td>Month</td><td>n/a</td></tr><tr><td><a href="channel/day-morphology.md">day</a></td><td>Day of the month</td><td>n/a</td></tr><tr><td><a href="channel/yr-morphology.md">yr</a></td><td>Year</td><td>n/a</td></tr><tr><td><a href="channel/unit-morphology.md">unit</a></td><td>ID of the object</td><td>n/a</td></tr><tr><td><a href="channel/gis_id-morphology.md">gis_id</a></td><td>Object ID in GIS</td><td>n/a</td></tr><tr><td><a href="channel/name-morphology.md">name</a></td><td>Name of the object or SWAT+ setup (basin outputs)</td><td>n/a</td></tr><tr><td><a href="channel/flo_in-morphology.md">flo_in</a></td><td>Channel inflow</td><td>m3/s</td></tr><tr><td><a href="channel/geo_bf.md">geo_bf</a></td><td>Groundwater baseflow entering the channel</td><td>m3/s</td></tr><tr><td><a href="channel/flo_out-morphology.md">flo_out</a></td><td>Channel outflow</td><td>m3/s</td></tr><tr><td><a href="channel/peakr.md">peakr</a></td><td>Peak rate</td><td>m3/s</td></tr><tr><td><a href="channel/sed_in-morphology.md">sed_in</a></td><td>Sediment inflow</td><td>tons</td></tr><tr><td><a href="channel/sed_out-morphology.md">sed_out</a></td><td>Sediment outflow</td><td>tons</td></tr><tr><td><a href="channel/washld.md">washld</a></td><td>Washload</td><td>tons</td></tr><tr><td><a href="channel/bedld.md">bedld</a></td><td>Bedload</td><td>tons</td></tr><tr><td><a href="channel/dep.md">dep</a></td><td>Deposition</td><td>tons</td></tr><tr><td><a href="channel/deg_btm-morphology.md">deg_btm</a></td><td>Channel bottom degradation sediment</td><td>tons</td></tr><tr><td><a href="channel/deg_bank-morphology.md">deg_bank</a></td><td>Channel bank degradation sediment</td><td>tons</td></tr><tr><td><a href="channel/hc_sed.md">hc_sed</a></td><td>Headcut sediment</td><td>tons</td></tr><tr><td><a href="channel/width.md">width</a></td><td>Channel width</td><td>m</td></tr><tr><td><a href="channel/depth.md">depth</a></td><td>Channel depth</td><td>m</td></tr><tr><td><a href="channel/slope.md">slope</a></td><td>Channel slope</td><td>m/m</td></tr><tr><td><a href="channel/deg_btm-morphology-2.md">deg_btm</a></td><td>Bottom degradation depth</td><td>m</td></tr><tr><td><a href="channel/deg_bank-morphology-2.md">deg_bank</a></td><td>Bank degradation depth</td><td>m</td></tr><tr><td><a href="channel/hc_len.md">hc_len</a></td><td>Headcut length</td><td>m</td></tr><tr><td><a href="channel/flo_in_mm.md">flo_in_mm</a></td><td>Channel inflow</td><td>mm</td></tr><tr><td><a href="channel/aqu_in_mm.md">aqu_in_mm</a></td><td>Aquifer inflow</td><td>mm</td></tr><tr><td><a href="channel/flo_out_mm.md">flo_out_mm</a></td><td>Channel outflow</td><td>mm</td></tr><tr><td><a href="channel/sed_stor-morphology.md">sed_stor</a></td><td>Sediment stored in the channel</td><td>tons</td></tr><tr><td><a href="channel/n_tot.md">n_tot</a></td><td>Total nitrogen</td><td>kg N</td></tr><tr><td><a href="channel/p_tot.md">p_tot</a></td><td>Total phosphorus</td><td>kg P</td></tr><tr><td><a href="channel/dep_bf.md">dep_bf</a></td><td>Bankfull flow-depth diagnostic</td><td>m/s</td></tr><tr><td><a href="channel/velav_bf.md">velav_bf</a></td><td>Average bankfull velocity</td><td>m/s</td></tr></tbody></table>

The source prints `dep_bf` with `m/s` in the units row. This page reproduces that output literally and does not reinterpret the unit from the field name.
{% endtab %}
{% endtabs %}

## Alternate channel routing output

The `channel_*` and `basin_cha_*` families are a separate 66-column routing and water-quality report; they do not use the `channel_sd_*` table above.

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
| [no3_in](no3_in-alternate-channel-routing-output.md) | Incoming nitrate nitrogen | kg N |
| [no3_out](no3_out-alternate-channel-routing-output.md) | Outgoing nitrate nitrogen | kg N |
| [orgp_in](orgp_in.md) | Incoming organic phosphorus | kg P |
| [orgp_out](orgp_out.md) | Outgoing organic phosphorus | kg P |
| [solp_in](solp_in-alternate-channel-routing-output.md) | Incoming soluble phosphorus | kg P |
| [solp_out](solp_out-alternate-channel-routing-output.md) | Outgoing soluble phosphorus | kg P |
| [nh4_in](nh4_in.md) | Incoming ammonium | kg |
| [nh4_out](nh4_out.md) | Outgoing ammonium | kg |
| [no2_in](no2_in-alternate-channel-routing-output.md) | Incoming nitrite | kg |
| [no2_out](no2_out-alternate-channel-routing-output.md) | Outgoing nitrite | kg |
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
| [tot_ssed](tot_ssed.md) | Total suspended sediment | tons |

`channel_sd_subday.txt` is a subdaily morphology report. It uses the morphology headings and adds the interval-specific rows selected by the subdaily channel option.
