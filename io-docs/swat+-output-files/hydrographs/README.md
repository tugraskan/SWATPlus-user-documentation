# Hydrographs

SWAT+ prints two hydrograph output files per time step, one for incoming and one for outgoing hydrographs. The printing of hydrographs is controlled by entering "y" or "n" in the _hyd_ line in [print.prt](../../introduction-1/simulation-settings/print.prt). Hydrographs can be printed at daily, monthly, yearly, and average annual time steps. The names of the hydrograph output files are as follows:&#x20;

* hydin\_day.txt
* hydout\_day.txt
* hydin\_mon.txt
* hydout\_mon.txt
* hydin\_yr.txt
* hydout\_yr.txt
* hydin\_aa.txt
* hydout\_aa.txt

The number of lines in the hydrograph output files depends on the number of connections between spatial objects defined in the SWAT+ setup. In the incoming hydrograph files, for each receiving object there will be one line  per source object it receives a hydrograph from. The number of lines per source object in the outgoing hydrograph files equals the number of receiving objects it sends hydrographs to.&#x20;

{% tabs %}
{% tab title="In" %}
| Field    | Description                                     | Unit |
| -------- | ----------------------------------------------- | ---- |
| [jday](jday-in.md)     | Julian Day                                      | n/a  |
| [mon](mon-in.md)      | Month                                           | n/a  |
| [day](day-in.md)      | Day of the month                                | n/a  |
| [yr](yr-in.md)       | Year                                            | n/a  |
| [name](name-in.md)     | Name of the receiving object                    | n/a  |
| [type](type-in.md)     | Type of the receiving object                    |      |
| [objtyp](objtyp-in.md)   | Type of the source object                       |      |
| [typ\_no](typ_no-in.md)  | ID of the source object                         |      |
| [hyd\_typ](hyd_typ-in.md) | Type of the incoming hydrograph                 |      |
| [fraction](fraction-in.md) | Fraction of the incoming hydrograph             |      |
| [flo](flo-in.md)      | Incoming flow                                   | m3/s |
| [sed](sed-in.md)      | Incoming sediment                               | tons |
| [orgn](orgn-in.md)     | Incoming organic nitrogen                       | kg   |
| [sedp](sedp-in.md)     | Incoming sediment phosphorus                    | kg   |
| [no3](no3-in.md)      | Incoming nitrate nitrogen                       | kg   |
| [solp](solp-in.md)     | Incoming soluble phosphorus                     | kg   |
| [chla](chla-in.md)     | Incoming Chlorophyll-a                          | kg   |
| [nh3](nh3-in.md)      | Incoming ammonia nitrogen                       | kg   |
| [no2](no2-in.md)      | Incoming nitrite nitrogen                       | kg   |
| [cbod](cbod-in.md)     | Incoming carbonaceous biochemical oxygen demand | kg   |
| [dox](dox-in.md)      | Incoming dissolved oxygen                       | kg   |
| [san](san-in.md)      | Incoming sand                                   | tons |
| [sil](sil-in.md)      | Incoming silt                                   | tons |
| [cla](cla-in.md)      | Incoming clay                                   | tons |
| [sag](sag-in.md)      | Incoming small aggregates                       | tons |
| [lag](lag-in.md)      | Incoming large aggregates                       | tons |
| [grv](grv-in.md)      | Incoming gravel                                 | tons |
| [null](null-in.md)     |                                                 |      |
{% endtab %}

{% tab title="Out" %}
| Field    | Description                                     | Unit |
| -------- | ----------------------------------------------- | ---- |
| [jday](jday-out.md)     | Julian Day                                      | n/a  |
| [mon](mon-out.md)      | Month                                           | n/a  |
| [day](day-out.md)      | Day of the month                                | n/a  |
| [yr](yr-out.md)       | Year                                            | n/a  |
| [name](name-out.md)     | Name of the source object                       | n/a  |
| [type](type-out.md)     | Type of the source object                       |      |
| [objtyp](objtyp-out.md)   | Type of the receiving object                    |      |
| [typ\_no](typ_no-out.md)  | ID of the receiving object                      |      |
| [hyd\_typ](hyd_typ-out.md) | Type of the outgoing hydrograph                 |      |
| [fraction](fraction-out.md) | Fraction of the outgoing hydrograph             |      |
| [flo](flo-out.md)      | Outgoing flow                                   | m3/s |
| [sed](sed-out.md)      | Outgoing sediment                               | tons |
| [orgn](orgn-out.md)     | Outgoing organic nitrogen                       | kg   |
| [sedp](sedp-out.md)     | Outgoing sediment phosphorus                    | kg   |
| [no3](no3-out.md)      | Outgoing nitrate nitrogen                       | kg   |
| [solp](solp-out.md)     | Outgoing soluble phosphorus                     | kg   |
| [chla](chla-out.md)     | Outgoing Chlorophyll-a                          | kg   |
| [nh3](nh3-out.md)      | Outgoing ammonia nitrogen                       | kg   |
| [no2](no2-out.md)      | Outgoing nitrite nitrogen                       | kg   |
| [cbod](cbod-out.md)     | Outgoing carbonaceous biochemical oxygen demand | kg   |
| [dox](dox-out.md)      | Outgoing dissolved oxygen                       | kg   |
| [san](san-out.md)      | Outgoing sand                                   | tons |
| [sil](sil-out.md)      | Outgoing silt                                   | tons |
| [cla](cla-out.md)      | Outgoing clay                                   | tons |
| [sag](sag-out.md)      | Outgoing small aggregates                       | tons |
| [lag](lag-out.md)      | Outgoing large aggregates                       | tons |
| [grv](grv-out.md)      | Outgoing gravel                                 | tons |
| [null](null-out.md)     |                                                 |      |
{% endtab %}
{% endtabs %}
