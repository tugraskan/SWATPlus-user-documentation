---
description: >-
  Baseflow rate at which all streams linked to an aquifer receive groundwater
  flow
---

# bf\_max

**Code reference:** `aqudb(i)%bf_max` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/aquifer_module.f90#L15)).

This parameter determines the daily groundwater flow amount needed for all channels linked to an aquifer to receive groundwater flow. If groundwater flow < _bf\_max_, the channels with the smallest drainage areas will stop receiving groundwater flow. The amount of groundwater flow a channel receives depends on the channel length.

{% hint style="info" %}
This parameter is only active when the file [**aqu\_cha.lin**](../../connectivity/aqu_cha.lin.md) is used instead of [**aquifer.con**](../../connectivity/hru.con/) to connect aquifers to channels.&#x20;
{% endhint %}
