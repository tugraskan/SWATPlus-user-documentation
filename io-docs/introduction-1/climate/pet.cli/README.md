---
description: "The pet.cli file supplies climate-station PET (potential evapotranspiration) measurement input records read by cli_petmeas.f90. Each record names a climate-station-specific file whose contents are opened and processed as PET input data for that station."
---

# pet.cli

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

The pet.cli file supplies climate-station PET (potential evapotranspiration) measurement input records read by cli_petmeas.f90. Each record names a climate-station-specific file whose contents are opened and processed as PET input data for that station.

The reader obtains the filename through `'pet.cli'`, `in_cli%pet_cli`.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record, then a header record, then a title record.

Before the data groups, the loading pass consumes a title record, then a header record.

### Record at line 63

Source condition/loop: `if (.not. i_exist .or. in_cli%pet_cli == "null") then / else > do > do i = 1, imax`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [filename](filename.md) | Name of the file containing potential evapotranspiration input data for the associated climate station | string | n/a | — | — |
