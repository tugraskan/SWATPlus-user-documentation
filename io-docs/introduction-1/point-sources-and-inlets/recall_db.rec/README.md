---
description: Recall constituent-name database records
---

# recall_db.rec

This file lists recall database records used in a simulation. Each row contains one record name, one name for each constituent group, and a description. The record name can be referenced by a reservoir decision-table action. The organic/mineral name is used to match outside-source water-quality recall definitions. In SWAT+ main (6f515368), the pesticide, pathogen, heavy-metal, salt, general-constituent, and description values are read but have no downstream use.

| Field | Description | Type |
| --- | --- | --- |
| [id](id-recall_db.rec.md) | ID of the recall database record | integer |
| [name](name.md) | Name of the recall database record; may be referenced by a reservoir decision-table file pointer | string |
| [om\_name](om_name.md) | Organic/mineral constituent name used to match an outside-source water-quality recall definition | string |
| [pest\_name](pest_name.md) | Pesticide constituent name; read but not used in SWAT+ main (6f515368) | string |
| [path\_name](path_name.md) | Pathogen constituent name; read but not used in SWAT+ main (6f515368) | string |
| [hmet\_name](hmet_name.md) | Heavy-metal constituent name; read but not used in SWAT+ main (6f515368) | string |
| [salt\_name](salt_name.md) | Salt constituent name; read but not used in SWAT+ main (6f515368) | string |
| [cst\_name](cst_name.md) | General constituent name; read but not used in SWAT+ main (6f515368) | string |
| [descrip](descrip.md) | Description of the recall database record; read but not used in SWAT+ main (6f515368) | string |
