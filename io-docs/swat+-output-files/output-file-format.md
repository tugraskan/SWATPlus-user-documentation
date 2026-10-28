# Output File Format

Some output files can be selected at daily, monthly, yearly, and average-annual intervals in [**print.prt**](../introduction-1/simulation-settings/print.prt/). Selected hydrographs for individual spatial objects can be written with [**object.prt**](../introduction-1/simulation-settings/object.prt/). Other files are produced only when a module or constituent is configured, and a small set records simulation status or diagnostics.

Most standard TXT reports are free-format, space-delimited files. Many begin with a run title followed by a printed field header and a units line. This is a common convention, not a universal three-line contract: salt and other constituent reports may include explanatory preamble lines, configured outputs may generate dynamic headings, and diagnostic or GWFlow reports can use specialized layouts.

When CSV output is enabled, standard `.csv` variants normally use the same printed field names as their TXT counterparts. Always interpret a file from the header it actually prints. The source variable name used to calculate a value can differ from that printed heading, and in a few known cases the printed header and data-row width do not agree; those cases are called out on the family page.
