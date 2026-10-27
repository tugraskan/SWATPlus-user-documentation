---
description: Pointer to the object data file
---

# 'obj'

**Code reference:** `ob(i)%props` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hydrograph_module.f90#L343)).

The pointer to the object data file identifies the corresponding record used by the object. For most connect files it references the unique ID in the listed object data file. The header of this column differs between connect files. Export coefficients have the known limitation below.

| Connect file   | Column header | Object data file                                                  |
| -------------- | ------------- | ----------------------------------------------------------------- |
| hru.con        | hru           | [**hru-data.hru**](../../hydrologic-response-units/hru-data.hru/) |
| hru-lte.con    | hlt           | [**hru-lte.hru**](../../hydrologic-response-units/hru-lte.hru/)   |
| rout\_unit.con | rtu           | [**rout\_unit.rtu**](../../routing-units/untitled/)               |
| aquifer.con    | aqu           | [**aquifer.aqu**](../../aquifers/aquifer.aqu/)                    |
| chandeg.con    | lcha          | [**channel-lte.cha**](../../channels/channel-lte.cha/)            |
| reservoir.con  | res           | [**reservoir.res**](../../reservoirs/reservoir.res/)              |
| recall.con     | rec           | [**recall.rec**](../../point-sources-and-inlets/recall.rec/)      |
| exco.con | exc | See known limitation below |
| delratio.con | dlr | delratio.del |
| outlet.con     | out           | No data file                                                      |

{% hint style="warning" %}
Export-coefficient records are selected by name during initialization, but by row position during routing. If the record order differs between `exco.exc` and `exco_om.exc`, these paths may select different values. This limitation applies to SWAT+ main at `6f515368`.
{% endhint %}
