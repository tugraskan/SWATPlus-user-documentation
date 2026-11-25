---
description: >-
  Baseflow rate at which all streams linked to an aquifer receive groundwater
  flow
---

# bf\_max

**Code reference:** `aqudb(i)%bf_max` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aquifer_module.f90#L15)).

Daily groundwater flow (mm) needed for every channel linked to an aquifer to receive groundwater flow. [`aqu_1d_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L282-L288) calculates the contributing channel length as follows:

$$
L_{\text{contrib}} = L_{\text{tot}} \times \frac{Q_{gw}}{\text{bf}_{\max}}
$$

where $L_{\text{tot}}$ is the total length of linked channels and $Q_{gw}$ is the day's groundwater flow (mm). Channels are tested in the order listed in **aqu\_cha.lin**. A channel receives groundwater only while its cumulative length is within $L_{\text{contrib}}$. When $Q_{gw}$ < _bf\_max_, channels further down the list stop receiving groundwater flow. Each contributing channel receives a share based on its length.

{% hint style="info" %}
This parameter is only active when [**aqu\_cha.lin**](../../connectivity/aqu_cha.lin.md) is used instead of [**aquifer.con**](../../connectivity/hru.con/) to connect aquifers to channels. In that case _bf\_max_ must be greater than 0, because it is used as a divisor.
{% endhint %}
