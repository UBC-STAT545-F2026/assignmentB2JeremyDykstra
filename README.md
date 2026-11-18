README
================
2026-11-17

# Description of the package

This package is useful for counting missing values for various groups.
There are two main features of this package, both focused on producing a
tibble output table with missing values. The first feature is to create
an ungrouped missing values table for different columns. The second
feature is to also display missing values, grouped by a specified
variable in the output table.

# Installation instructions

This package is available for free public download (with citation) from
GitHub. Install the “devtools” package if you do not already have it on
your R studio. Use the following code to directly install the package by
pasting this message directly into the R console. If successfully
installed you are likely to get a message like this at the end of the
loading code in your R console “DONE (assignmentB2JeremyDykstra)”.

``` r
remotes::install_github(
  "UBC-STAT545-F2026/assignmentB2JeremyDykstra",
  ref = "0.1.0"
)
```

# How to use this package, with examples

After installing the package from GitHub, load the package into your R
studio using the below code.

``` r
library(assignmentB2JeremyDykstra)
```

The primary function in the package is named
“count_all_missing_by_group”. You can call the function by selecting the
following parameters.

Parameters in the function 1. data (name of data) 2. group_col (Variable
name) 3. .groups = “drop” (ungrouped output) or .groups = “keep”
(grouped table)

When you put it all together it looks like this: function(data,
group_col, .groups = “drop”).

See below for two examples using an air quality dataset by Month in
either the ungrouped or grouped table.

``` r
count_all_missing_by_group(airquality, Month) #ungrouped table
```

    ## # A tibble: 5 × 6
    ##   Month Ozone Solar.R  Wind  Temp   Day
    ##   <int> <int>   <int> <int> <int> <int>
    ## 1     5     5       4     0     0     0
    ## 2     6    21       0     0     0     0
    ## 3     7     5       0     0     0     0
    ## 4     8     5       3     0     0     0
    ## 5     9     1       0     0     0     0

``` r
count_all_missing_by_group(airquality, Month, .groups = "keep") #grouped table
```

    ## # A tibble: 5 × 6
    ## # Groups:   Month [5]
    ##   Month Ozone Solar.R  Wind  Temp   Day
    ##   <int> <int>   <int> <int> <int> <int>
    ## 1     5     5       4     0     0     0
    ## 2     6    21       0     0     0     0
    ## 3     7     5       0     0     0     0
    ## 4     8     5       3     0     0     0
    ## 5     9     1       0     0     0     0
