# fertilizer.frt_cs

Constituent composition of fertilizer for the SeO4 and SeO3 species and boron. Application routines multiply these mass fractions by the amount of fertilizer applied.

The first line is a title and the second line is a header. Each subsequent record contains the fields below, in this order. There is no separate record-count line. The reader requests exactly one record per fertilizer database entry (db_mx%fertparm). Keep these records in the same order as the fertilizer database; the name field is not used to reorder them.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [fertnm](fertnm.md) | Fertilizer name label | string | n/a | — | — |
| [seo4](seo4.md) | SeO4 constituent mass fraction | real | kg/kg fertilizer | — | — |
| [seo3](seo3.md) | SeO3 constituent mass fraction | real | kg/kg fertilizer | — | — |
| [boron](boron.md) | boron constituent mass fraction | real | kg/kg fertilizer | — | — |

Recommended defaults and ranges are not specified by this page. The dash does not imply a default of zero.

The values are mass per mass of fertilizer: multiplying kg fertilizer/ha by kg constituent/kg fertilizer gives kg constituent/ha. They are not absolute application loads in kg/ha, despite the older source comments. No required sum of the constituent values is established here.
