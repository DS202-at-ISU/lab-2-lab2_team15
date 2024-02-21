
<!-- README.md is generated from README.Rmd. Please edit the README.Rmd file -->

# Lab report \#1

<<<<<<< HEAD
=======
# \<\<\<\<\<\<\< HEAD


## Question 1:

``` r
str(ames)
```

    ## Classes 'tbl_df', 'tbl' and 'data.frame':    6935 obs. of  16 variables:
    ##  $ Parcel ID            : chr  "0903202160" "0907428215" "0909428070" "0923203160" ...
    ##  $ Address              : chr  "1024 RIDGEWOOD AVE, AMES" "4503 TWAIN CIR UNIT 105, AMES" "2030 MCCARTHY RD, AMES" "3404 EMERALD DR, AMES" ...
    ##  $ Style                : Factor w/ 12 levels "1 1/2 Story Brick",..: 2 5 5 5 NA 9 5 5 5 5 ...
    ##  $ Occupancy            : Factor w/ 5 levels "Condominium",..: 2 1 2 3 NA 2 2 1 2 2 ...
    ##  $ Sale Date            : Date, format: "2022-08-12" "2022-08-04" ...
    ##  $ Sale Price           : num  181900 127100 0 245000 449664 ...
    ##  $ Multi Sale           : chr  NA NA NA NA ...
    ##  $ YearBuilt            : num  1940 2006 1951 1997 NA ...
    ##  $ Acres                : num  0.109 0.027 0.321 0.103 0.287 0.494 0.172 0.023 0.285 0.172 ...
    ##  $ TotalLivingArea (sf) : num  1030 771 1456 1289 NA ...
    ##  $ Bedrooms             : num  2 1 3 4 NA 4 5 1 3 4 ...
    ##  $ FinishedBsmtArea (sf): num  NA NA 1261 890 NA ...
    ##  $ LotArea(sf)          : num  4740 1181 14000 4500 12493 ...
    ##  $ AC                   : chr  "Yes" "Yes" "Yes" "Yes" ...
    ##  $ FirePlace            : chr  "Yes" "No" "No" "No" ...
    ##  $ Neighborhood         : Factor w/ 42 levels "(0) None","(13) Apts: Campus",..: 15 40 19 18 6 24 14 40 13 23 ...

``` r
?ames
```

    ## starting httpd help server ... done

The variables are:  
- Parcel ID: a chr variable that is a character ID number.  
- Address: a chr variable that holds the property address in Ames, IA  
- Style: factor variable detailing the type of housing  
- Occupancy: factor variable of the type of housing  
- Sale Date: date in chr format that is the date of house sale  
- Sale Price: a numerical variable that holds the sales price (in US
dollar)  
- Multi Sale: a chr that is a value if the sale was part of a package
and null if not  
- YearBuilt: an integer variable that hold the year that the house was
built  
- Acres: a numerical variable that holds the acres of the lot that the
house is built on  
- TotalLivingArea: a numerical variable of the total living are in
square feet  
- Bedrooms: a numerical variable that tells the number of bedrooms  
- FinishedBsmtArea: a numerical value that tells the total area of the
finished basement in square feet and is null if the basement is not
finished  
- LotArea: a numerical variable that is the total lot area in square
feet  
- AC: a chr variable that is either “Yes” or “No” depending on if the
property has AC or not  
- FirePlace: a chr variable that is either “Yes” or “No” depending on if
the property has a fireplace or not  
- Neighborhood: a factor variable, where the levels indicate
neighborhood are in Ames

<<<<<<< HEAD
=======
## Question 2

A variable that seems the most important is “sale Price”. When drawing
conclusions from this data, the most useful application I believe would
be predicting prices of homes with this variable. So it makes sense for
Sale Price to be our main variable.(Andrew)

## Question 3 (Vanessa):

``` r
library(classdata)
View(ames)
```

Range of the Variable:

``` r
summary(ames$`Sale Price`)
```

    ##     Min.  1st Qu.   Median     Mean  3rd Qu.     Max. 
    ##        0        0   170900  1017479   280000 20500000

Histogram: There is something odd about the histogram, as it appears to
show sale prices of 0s.

``` r
library(ggplot2)
ggplot(ames, aes( x=`Sale Price`)) + geom_histogram(binwidth = 10000000)
```

![](README_files/figure-gfm/unnamed-chunk-4-1.png)<!-- -->

## Question 4:

### Emily Maruska - Finished Basement Area

<<<<<<< HEAD
>>>>>>> f0ed776e24ff50bdcd248d393dd8152cdcdc7c0e
=======
``` r
summary(ames$`FinishedBsmtArea (sf)`)
```

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max.    NA's 
    ##    10.0   474.0   727.0   776.7  1011.0  6496.0    2682

``` r
ggplot(ames, aes(x = ames$`FinishedBsmtArea (sf)`)) + geom_histogram()
```

    ## Warning: Use of `` ames$`FinishedBsmtArea (sf)` `` is discouraged.
    ## ℹ Use `FinishedBsmtArea (sf)` instead.

    ## `stat_bin()` using `bins = 30`. Pick better value with `binwidth`.

    ## Warning: Removed 2682 rows containing non-finite values (`stat_bin()`).

![](README_files/figure-gfm/unnamed-chunk-5-1.png)<!-- --> There is a
distinct pattern in the histogram that shows that most of the houses
that have a finished basement have a basement area that is roughly
around 1000 square feet. There are, however, a few houses that have
extremely large basements in comparison.

``` r
ggplot(ames, aes(x = ames$`FinishedBsmtArea (sf)`, y = ames$`Sale Price`)) + ylim(0, 1300000) + geom_point()
```

    ## Warning: Use of `` ames$`FinishedBsmtArea (sf)` `` is discouraged.
    ## ℹ Use `FinishedBsmtArea (sf)` instead.

    ## Warning: Use of `` ames$`Sale Price` `` is discouraged.
    ## ℹ Use `Sale Price` instead.

    ## Warning: Removed 2682 rows containing missing values (`geom_point()`).

![](README_files/figure-gfm/unnamed-chunk-6-1.png)<!-- -->

In comparing the finished basement area to the sales price, there is a
pretty clear pattern that generally the larger the finished basement,
the larger the sales price is. There are a decent amount of outliers,
such as houses that sold for very little cost but with a finished
basement are of roughly 2000, or houses that sold for an extremely high
cost with a finished basement of 2000 as well. This also reflects the
oddities found in question 3 as there are also many values in this
scatter plot that indicate a finished basement in a house that sold for
no cost.



Follow the instructions posted at
<https://ds202-at-isu.github.io/labs.html> for the lab assignment. The
work is meant to be finished during the lab time, but you have time
until Monday evening to polish things.

Include your answers in this document (Rmd file). Make sure that it
knits properly (into the md file). Upload both the Rmd and the md file
to your repository.

All submissions to the github repo will be automatically uploaded for
grading once the due date is passed. Submit a link to your repository on
Canvas (only one submission per team) to signal to the instructors that
you are done with your submission.

### Andrew Kinneer - Year Built
For my variable I chose "YearBuilt"
```{R}
range(ames$YearBuilt, na.rm = TRUE)
```
The range of this variable is from 0 - 2022
Here is the distribution of YearBuilt. There are a few outliers at 0 which are removed in the chart
```{R}
library(ggplot2)
ggplot(ames, aes(x = YearBuilt)) +
  geom_bar(binwidth = 10,color = "skyblue") +
  labs(title = "Count of YearBuilt", x = "Year", y = "Count") +
  xlim(1880, 2022)
```

Below you can see the comparison of YearBuilt to SalePrice. At first there seems to be no increase in SalePrice over the years. At around 1960 there became a general increase in SalePrice with it peaking in the current year. This does not explain the previous oddities mentioned in #3 with the zeros.

```{R}
ggplot(ames, aes(x = YearBuilt, y = `Sale Price`)) +
  geom_point(color = "blue", alpha = 0.7) +
  labs(title = "Scatter Plot of YearBuilt vs Sale Price",
       x = "Year Built",
       y = "Sale Price") +
  xlim(1880, 2022) +
  ylim(1, 1500000)
```


