# Connectivity

Gravity-controlled flow is routed from one spatial object to the next using so-called connect files, which are available for the following objects:

| Object             | Connect file   |
| ------------------ | -------------- |
| HRU                | hru.con        |
| HRU-lte            | hru-lte.con    |
| Routing Unit       | rout\_unit.con |
| Aquifer            | aquifer.con    |
| SWAT-DEG channel   | chandeg.con    |
| SWAT channel       | channel.con    |
| GWFlow cell        | gwflow.con     |
| Reservoir          | reservoir.con  |
| Point source/inlet | recall.con     |
| Export coefficient | exco.con       |
| Delivery ratio     | delratio.con   |
| Outlet             | outlet.con     |

All connect files have the exact same structure, so to avoid repetition it is only described once instead of for every spatial object (see [**'object'.con**](hru.con/)). The file names are set on the `connect` line of file.cio ([`readcio_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readcio_read.f90#L44)). Connections are set when the model starts ([`hyd_connect.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hyd_connect.f90#L215-L403)); in SWAT+ main (6f515368), decision tables do not change them.

To distribute an aquifer's return flow among several channels, use [**aqu\_cha.lin**](aqu_cha.lin.md). It is read in addition to aquifer.con, not instead of it. [**chan-surf.lin**](chan_surf.lin.md) links channels to the HRUs of their flood plain.
