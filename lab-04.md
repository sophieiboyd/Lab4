Lab 04 - La Quinta is Spanish for next to Denny’s, Pt. 1
================
Sophie Boyd
2-6-26

### Load packages and data

``` r
library(tidyverse) 
library(dsbox)
```

``` r
states <- read_csv("data/states.csv")
```

### Exercise 1

``` r
view(dennys)
nrow(dennys)
```

    ## [1] 1643

``` r
ncol(dennys)
```

    ## [1] 6

The Denny’s dataset contains 1643 observations of 6 variables. Each row
represents one Denny’s establishment. The variables are address, city,
state, zip code, longitude, and latitude.

### Exercise 2

``` r
view(laquinta)
nrow(laquinta)
```

    ## [1] 909

``` r
ncol(laquinta)
```

    ## [1] 6

The La Quinta dataset contains 909 observations of 6 variables. Each row
represents one La Quinta establishment. The variables are the same as
the Denny’s dataset: address, city, state, zip code, longitude, and
latitude.

### Exercise 3

The La Quinta website lists many locations outside of the US, including
in Canada, Mexico, China, New Zealand, Georgia, Turkiye, the UAE,
Colombia, and Ecuador.

The Denny’s website seems to only contain locations in the US.

### Exercise 4

One way to determine if locations in either dataset are outside of the
US would be to look at the values on the “state” variable. If the values
are missing or do not indicate a US state, this would confirm that the
establishment is located outside of the US.

### Exercise 5

``` r
dennys %>%
  filter(!(state %in% states$abbreviation))
```

    ## # A tibble: 0 × 6
    ## # ℹ 6 variables: address <chr>, city <chr>, state <chr>, zip <chr>,
    ## #   longitude <dbl>, latitude <dbl>

There do not appear to be any Denny’s locations outside of the US.

### Exercise 6

``` r
dennys <- dennys %>%
  mutate(country = "United States")
```

### Exercise 7
