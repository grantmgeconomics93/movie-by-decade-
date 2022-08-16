Untitled
================
2022-08-16

``` r
library(dplyr)
```

    ## Warning: package 'dplyr' was built under R version 4.1.3

    ## 
    ## Attaching package: 'dplyr'

    ## The following objects are masked from 'package:stats':
    ## 
    ##     filter, lag

    ## The following objects are masked from 'package:base':
    ## 
    ##     intersect, setdiff, setequal, union

``` r
library(tidyr)
```

    ## Warning: package 'tidyr' was built under R version 4.1.3

``` r
Movies=mutate(Movies,"do people really mess with it like that "=dense_rank(vote_average))
```

``` r
Movies$aphabet=sort(Movies$title...4)
```

``` r
Movies$releasedate2=Movies$release_date%>%as.character()
```

``` r
t=separate(Movies,releasedate2,c("date","year"),"-")
```

    ## Warning: Expected 2 pieces. Additional pieces discarded in 9980 rows [1, 2, 3,
    ## 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, ...].

``` r
Movies$"1910"=ifelse(t$date<1910,Movies$title...4,"na")
```

Note that the `echo = FALSE` parameter was added to the code chunk to
prevent printing of the R code that generated the plot.
