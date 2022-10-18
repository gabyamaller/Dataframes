---
title: "Realtor Data"
author: "Gabriela Amaller"
date: "2022-10-18"
output: 
  html_document:
    keep_md: true
    toc: true
    toc_float: true
    code_folding: hide
    fig_height: 6
    fig_width: 12
    fig_align: 'center'
   
---


```r
library(mosaic)
library(pander)
library(tidyverse)
library(DT)
library(dplyr)
library(car)
```


```r
data = read_csv(file="realtor-data.csv")
```

```r
df <- data %>% 
  filter(state == "Massachusetts")

df
```

```
## # A tibble: 175,248 × 12
##    status   price   bed  bath acre_…¹ full_…² street city  state zip_c…³ house…⁴
##    <chr>    <dbl> <dbl> <dbl>   <dbl> <chr>   <chr>  <chr> <chr>   <dbl>   <dbl>
##  1 for_sa… 180000     2     1    0.34 23 Moo… 23 Mo… Agaw… Mass…    1001     676
##  2 for_sa…  25000    NA    NA    3.41 Leonar… Leona… Agaw… Mass…    1001      NA
##  3 for_sa… 169900     2     2   NA    420 Ma… 420 M… Agaw… Mass…    1001     892
##  4 for_sa… 242000     2     2   NA    2A Man… 2A Ma… Agaw… Mass…    1001    1428
##  5 for_sa… 299950     2     2   NA    19 Cas… 19 Ca… Agaw… Mass…    1001    1659
##  6 for_sa… 239900     3     1    0.46 270 So… 270 S… Agaw… Mass…    1001    1196
##  7 for_sa… 525000     3     3    0.45 955 Ri… 955 R… Agaw… Mass…    1001    2314
##  8 for_sa… 289900     3     2    0.36 82 Har… 82 Ha… Agaw… Mass…    1001    1276
##  9 for_sa… 239900     2     3   NA    15 Ash… 15 As… Agaw… Mass…    1001    1229
## 10 for_sa… 249900     2     1   NA    181 Br… 181 B… Agaw… Mass…    1001     860
## # … with 175,238 more rows, 1 more variable: sold_date <date>, and abbreviated
## #   variable names ¹​acre_lot, ²​full_address, ³​zip_code, ⁴​house_size
```





```r
#remove na's 
dataframe <-df %>% 
  drop_na
dataframe
```

```
## # A tibble: 51,961 × 12
##    status   price   bed  bath acre_…¹ full_…² street city  state zip_c…³ house…⁴
##    <chr>    <dbl> <dbl> <dbl>   <dbl> <chr>   <chr>  <chr> <chr>   <dbl>   <dbl>
##  1 for_sa… 525000     3     3    0.45 955 Ri… 955 R… Agaw… Mass…    1001    2314
##  2 for_sa… 289900     3     2    0.36 82 Har… 82 Ha… Agaw… Mass…    1001    1276
##  3 for_sa… 384900     3     2    0.46 45 Ham… 45 Ha… Agaw… Mass…    1001    1476
##  4 for_sa… 199999     3     2    1.76 88 Sou… 88 So… Agaw… Mass…    1001    1968
##  5 for_sa… 419000     4     2    2    57 Amh… 57 Am… Pelh… Mass…    1002    1607
##  6 for_sa… 745000     4     3    0.56 103 Su… 103 S… Amhe… Mass…    1002    2847
##  7 for_sa… 875000     4     4    1.5  61 S V… 61 S … Pelh… Mass…    1002    4366
##  8 for_sa… 699900     4     4    0.77 12 Ket… 12 Ke… Amhe… Mass…    1002    3879
##  9 for_sa… 275000     3     2    0.16 5 Bedf… 5 Bed… Amhe… Mass…    1002    1280
## 10 for_sa… 415000     4     2    0.49 257 Po… 257 P… Amhe… Mass…    1002    1814
## # … with 51,951 more rows, 1 more variable: sold_date <date>, and abbreviated
## #   variable names ¹​acre_lot, ²​full_address, ³​zip_code, ⁴​house_size
```

```r
 #install.packages("writexl")
#export r to excel 
library("writexl")
#write_xlsx(the dataframe name,"path to store the Excel file\\file name.xlsx")


write_xlsx(dataframe,"~/Desktop/realtor-data.xlsx")
```

