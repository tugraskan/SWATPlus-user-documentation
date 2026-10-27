---
description: Object type of the receiving object
---

# rcv\_ob

{% hint style="warning" %}
This is a historical `water_allocation.wro` field. For the reviewed main layout, see [place_of_use.wro](../place_of_use.wro.md) and [point_of_diver.wro](../point_of_diver.wro.md). The original description below is retained as historical reference.
{% endhint %}

The receiving object can be specified by entering "cha" for channels, "res" for reservoirs, or "aqu" for aquifers. If non of these three options is entered, SWAT+ assumes that the water is transferred to an object outside the modeled watershed and thus lost from the system. By entering a name in this column, the user can make sure that the receiving object is included in the water allocation output file.&#x20;

| Object type              | Description                                                                        |
| ------------------------ | ---------------------------------------------------------------------------------- |
| cha                      | Channel                                                                            |
| res                      | Reservoir                                                                          |
| aqu                      | Aquifer                                                                            |
| Name of receiving object | User-defined name of an object that is assumed to be located outside the watershed |
