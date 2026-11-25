---
description: This file is used to connect an aquifer to multiple channels.
---

# aqu\_cha.lin

This file distributes the return flow of an aquifer among several SWAT-DEG channels. It is optional and is [read after aquifer.con](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hyd_connect.f90#L144-L147), in addition to it. The file name is set on the `link` line of file.cio; the default is `aqu_cha.lin`, and a missing file or `null` turns the option off ([`aqu2d_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu2d_read.f90#L28-L73)).

The first line is a title and the second a header. Each following line is one aquifer:

| Value    | Description |
| -------- | ----------- |
| id       | Aquifer number ([id](hru.con/id.md) in aquifer.con) |
| name     | Name of the record |
| elem_tot | Number of values that follow |
| elements | SWAT-DEG channel numbers (row positions in chandeg.con). A negative number ends a range: `1 -5` means channels 1 to 5 |

Each channel can be linked to one aquifer.

**How the flow is distributed:** SWAT+ computes the length of stream that currently receives groundwater,

$$L_{\text{contrib}} = L_{\text{tot}} \times q / q_{\text{max}}$$

where $L_{\text{tot}}$ is the total length of the listed channels, $q$ is the aquifer return flow of the day and $q_{\text{max}}$ is [bf\_max](../aquifers/aquifer.aqu/flo_max.md). Channels with small drainage areas [dry up first](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L280-L304), and the return flow is shared among the contributing channels in proportion to their length. The water is [added to the channel inflow](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_control3.f90#L117-L143).

{% hint style="warning" %}
Do not also send the `tot` hydrograph of a listed aquifer to these channels in aquifer.con, or the channels receive the water twice.
{% endhint %}

{% hint style="warning" %}
In SWAT+ main (6f515368), the channel length used here is [looked up in hyd-sed-lte.cha](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu2d_init.f90#L35-L37) with the channel's `lcha` number from chandeg.con, instead of through channel-lte.cha. The length is the intended one only when both point to the same record.
{% endhint %}
