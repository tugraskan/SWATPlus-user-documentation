---
description: This file links channels to the HRUs of their flood plain.
---

# chan-surf.lin

This optional file lists the HRUs or routing units in the flood plain of each SWAT-DEG channel. The file name is set on the `link` line of file.cio; the [default](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/input_file_module.f90#L151-L154) is `chan-surf.lin`. Use `null` there if the file is not used.

The first line is a title, the second the number of channel records, and the third a header. Each following line is [one channel](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/overbank_read.f90#L57-L70):

| Value   | Description |
| ------- | ----------- |
| id      | SWAT-DEG channel number (row position in chandeg.con) |
| name    | Name of the record |
| obj_tot | Number of type and number pairs that follow |
| type    | `hru` or `ru` |
| number  | Number of the HRU or routing unit |

On SWAT+ dev, when the overbank fraction of a channel's flow exceeds 0.05, overbank water [fills the wetlands](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L137-L207) of the linked HRUs. HRUs without a wetland ([surf\_stor](../hydrologic-response-units/hru-data.hru/surf_stor.md)) receive no water this way.

{% hint style="warning" %}
In SWAT+ main (6f515368), type `ru` [uses the element numbers of the routing unit as HRU numbers](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_surf_link.f90#L48-L58). The two must be the same; otherwise list the HRUs with type `hru`.
{% endhint %}

{% hint style="warning" %}
If file.cio names a file that does not exist instead of `null`, SWAT+ [opens it anyway](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/overbank_read.f90#L28-L31), which creates an empty file.
{% endhint %}
