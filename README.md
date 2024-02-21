
<!-- README.md is generated from README.Rmd. Please edit the README.Rmd file -->

# Lab report \#1

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
