# Water Allocation

In SWAT+ main (`6f515368`), water-allocation inputs are split between two `file.cio`-selected routing files and twelve auxiliary `.wal` files opened directly from the simulation working directory.

## Files Selected via `file.cio`

Declared in [`input_file_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/input_file_module.f90#L144-L148) and read in [`readcio_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readcio_read.f90#L64) and [`water_allocation_read.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/water_allocation_read.f90#L1-L256):

- [place_of_use.wro](place_of_use.wro/README.md): places of use (POUs), their points of diversion (PODs), and their points of return (PORs).
- [point_of_diver.wro](point_of_diver.wro/README.md): points of diversion (PODs) and their associated POUs.

## Working-Directory `.wal` Files

Opened by hardcoded filename from [`main.f90.in`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/main.f90.in#L104-L114) (not listed in `file.cio`):

- [wtps_wuses.wal](wtps_wuses.wal/README.md): active water treatment plant and water-use object lists.
- [om_treat.wal](om_treat.wal/README.md), [om_use.wal](om_use.wal/README.md), [om_osrc.wal](om_osrc.wal/README.md): named organic/mineral flow-fraction and concentration records for treatment plants, water uses, and outside sources.
- [water_treat.wal](water_treat.wal/README.md), [water_use.wal](water_use.wal/README.md), [outside_src.wal](outside_src.wal/README.md): water treatment plant, water-use, and outside-source definitions.
- [outside_rcv.wal](outside_rcv.wal/README.md): outside-basin receiving objects (reader in [`water_orcv_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_orcv_read.f90#L1-L54) is not called in `6f515368`).
- [water_tower.wal](water_tower.wal/README.md), [water_pipe.wal](water_pipe.wal/README.md), [water_canal.wal](water_canal.wal/README.md): conveyance and storage objects.
- [water_hru_irr.wal](water_hru_irr.wal/README.md): irrigation HRU groups and demand decision tables.

{% hint style="warning" %}
Several `.wal` and `.wro` readers in `6f515368` have loop-exit, file-existence guard, or call-order quirks (documented on each file's page).
{% endhint %}
