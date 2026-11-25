---
description: "Counts and names of the constituents to simulate in each of five groups."
---

# constituents.cs

This file sets the constituents SWAT+ simulates. Its name is the fifth file name on the `simulation` line of [file.cio](../master-file-file.cio.md); the default is `constituents.cs` ([`input_file_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/input_file_module.f90#L8-L14)). If the file is missing or the name is `null`, every count is 0 and no warning is given ([`constit_db_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constit_db_read.f90#L25-L31)).

## File layout

The file has a title line, then a count line and a names line for each group, always in the order below ([`constit_db_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constit_db_read.f90#L33-L65)). There are no column headings.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [num_pests](constituents.cs/num_pests.md) | Number of pesticides | integer | n/a | 0 | 0 or more |
| [pests](constituents.cs/pests.md) | Pesticide names | list of text (16 characters each) | n/a | — | names in pesticide.pes |
| [num_paths](constituents.cs/num_paths.md) | Number of pathogens | integer | n/a | 0 | 0 or more |
| [paths](constituents.cs/paths.md) | Pathogen names | list of text (16 characters each) | n/a | — | names in pathogens.pth |
| [num_metals](constituents.cs/num_metals.md) | Number of heavy metals | integer | n/a | 0 | 0 or more |
| [metals](constituents.cs/metals.md) | Heavy-metal names | list of text (16 characters each) | n/a | — | — |
| [num_salts](constituents.cs/num_salts.md) | Number of salt ions | integer | n/a | 0 | 0 or 8 |
| [salts](constituents.cs/salts.md) | Salt-ion names, in a fixed order | list of text (16 characters each) | n/a | — | see field page |
| [num_cs](constituents.cs/num_cs.md) | Number of other constituents | integer | n/a | 0 | 0 or 3 |
| [cs](constituents.cs/cs.md) | Names of the other constituents, in a fixed order | list of text (16 characters each) | n/a | — | see field page |

## Example

```
constituents.cs: one pesticide, eight salt ions, selenium and boron
1
atrazine
0
null
0
null
8
so4 ca mg na k cl co3 hco3
3
seo4 seo3 boron
```

## Reading rules

* Keep a names line even when the count is 0. SWAT+ still reads one line there, so leave it blank or enter `null`.
* List exactly as many names as the count, separated by spaces. With too few names, SWAT+ takes the rest from the following lines and the later counts are read from the wrong places. Extra names on the line are ignored.
* If the file ends early, reading stops without a message and the remaining groups are not set up ([`constit_db_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constit_db_read.f90#L33-L65)).
