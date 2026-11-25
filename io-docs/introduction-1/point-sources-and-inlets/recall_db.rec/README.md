---
description: Recall constituent-name database records
---

# recall\_db.rec

This file lists recall database records used in a simulation. SWAT+ looks for `recall_db.rec` in the simulation working directory (it is not selected through `file.cio`) and reads it with [`recalldb_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recalldb_read.f90#L24-L59). Each row contains one integer ID, one record name, one name for each constituent group, and a description ([`recalldb_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recalldb_read.f90#L49)).

The record `name` can be referenced by a reservoir release decision-table action (`file_pointer` in [`dtbl_res_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dtbl_res_read.f90#L92)), and `om_name` is matched against `org_min_name` in water-allocation concentration definitions ([`water_osrc_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_osrc_read.f90#L79), [`water_treatment_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_treatment_read.f90#L83), and [`water_use_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_use_read.f90#L80)). Note that while [`wallo_start_day.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_start_day.f90#L73), [`wallo_treatment.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_treatment.f90#L45), and [`wallo_use.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_use.f90#L41) read `recall_db(irec)%iorg_min`, that integer index is never assigned in [`recalldb_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recalldb_read.f90#L1-L61). The pesticide, pathogen, heavy-metal, salt, general-constituent, and description columns are parsed but unused in SWAT+ main (`6f515368`).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [id](id-recall_db.rec.md) | ID of the recall database record | integer | n/a | — | — |
| [name](name.md) | Name of the recall database record; referenced by reservoir decision-table `file_pointer` | string | n/a | — | — |
| [om\_name](om_name.md) | Organic/mineral constituent name matched in water-allocation concentration tables | string | n/a | — | — |
| [pest\_name](pest_name.md) | Pesticide constituent name; read but not used in SWAT+ main (`6f515368`) | string | n/a | — | — |
| [path\_name](path_name.md) | Pathogen constituent name; read but not used in SWAT+ main (`6f515368`) | string | n/a | — | — |
| [hmet\_name](hmet_name.md) | Heavy-metal constituent name; read but not used in SWAT+ main (`6f515368`) | string | n/a | — | — |
| [salt\_name](salt_name.md) | Salt constituent name; read but not used in SWAT+ main (`6f515368`) | string | n/a | — | — |
| [cst\_name](cst_name.md) | General constituent name; read but not used in SWAT+ main (`6f515368`) | string | n/a | — | — |
| [descrip](descrip.md) | Description of the recall database record; read but not used in SWAT+ main (`6f515368`) | string | n/a | — | — |
