---
title: 'Final Proposal'
author: "Roba Abbajabal, Conor O'Shea, Aadhi Subbiah, Daniel Nass"
date: "11/11/2023"
output: html_document
---

### Introduction
- For our research, we wished to analyze transportation safety in the US by state from 2010-2021.
- This involved observing fatalities by state and year, and then connecting that information with outside sources.
- This research particularly interests us, because we wish to find reasons of what may cause safer roads.


### Research Title: An Analysis on Transportation Safety in the US
### Team Members: Roba Abbajabal, Conor O'Shea, Aadhi Subbiah, Daniel Nass

#### Description of Data: 
This data set contains information from 2010-2021 regarding fatal vehicular accidents that have occured on highways within the United States by state/territory.
The data can be acessed at the following link: https://www.bts.gov/browse-statistical-products-and-data/state-transportation-statistics/transportation-safety
The varibles included in this dataset are as follows: 
- State: the state that the information comes from
- Fatality Type: A factor of 14 different types of fatalities (such as highway fatalities, SUV fatalities, etc.)
  - Highway Fatalities
  - Passenger Car Fatalities
  - SUV Fatalities
  - Pickup Truck Fatalities
  - Van Fatalities
  - Other Light Truck Fatalities
  - Motorcycle Fatalities
  - Bus Fatalities
  - Large Truck Fatalities
  - Pedalcyclist Fatalities
  - Pedestrian Fatalities
  - Other Nonoccupant Fatalities
  - Other Vehicle Fatalities
  - Unknown Person Type Fatalities
- Year: The year, from 2010 to 2021, of the number of a specific type of fatality in a state occured.
- TotalFatalities: the sum of all fatalities for each FatalityType and by year for overall and by each state.

#### Supplementary Datasets Used:
State Population Totals: 2010-2020
Our dataset from Bureau of Transportation Safety contains information 
from 2010-2021 regarding fatal vehicular accidents that have occurred 
on highways within the United States by state/territory.
The data can be accessed at the following link: https://www.census.gov/programs-surveys/popest/technical-documentation/research/evaluation-estimates/2020-evaluation-estimates/2010s-state-total.html
Usage: This dataset will be used for reporting the number of fatalities by state by capita.
The varibles included in this dataset are as follows: 
- Name: The state that information comes from.
- POPESTIMATE([2010-2021]): The population estimates for year ([2010-2021]).

#### Investigations: 
- What is the leading cause of highway fatalities overall/by state?
- What states, if any, have stark contrasts in vehicular fatalities? 
- Do these states have any laws or regulations that would cause this?
- Do any types of vehicular fatalities correlate with another?
- Have counts of certain types of vehicular fatalities increased or decreased over time?
- How did the COVID-19 pandemic during 2021 affect traffic fatalities?

#### Main:
The data does not account directly for population density. 
The data is raw numbers, and in order to get a better insight into what the
data means we have to look at it by state.

The first cases of COVID-19 reached the US in January 2020, and the Trump Administration
declared a nationwide emergency on the COVID-19 pandemic in March 2021.
(https://www.cdc.gov/museum/timeline/covid19.html).

However, according to the National Highway Traffic Safety Administration,
the number of fatal traffic crashes increased by 6.8%. This would seem strange,
considering that less people overall were driving on the road without the need to
commute to work.
(https://www.nhtsa.gov/press-releases/2020-traffic-crash-data-fatalities)

Megan McArdle, a columnist the Washington Post, indicated that this may be due to an
increase in young and risky male drivers taking advantage of empty COVID-era roads.
A study done by the AAA Foundation for Traffic Safety indicated that young males were
the only people who indicated that they were driving more during the COVID pandemic -
taking their risky driving with them.
(https://www.washingtonpost.com/opinions/2022/03/10/pandemic-risky-driving-maybe-here-to-stay/).

Light Truck fatalities seems to be an exception to these sudden spike of fatal accidents
during the COVID-19 pandemic, due to young male drivers being less likely to own light trucks.

In addition, according to Michael Wilbur, a PHD Student in Vanderbilt University, in a paper 
published in the Transportation Research Record: Journal of the Transportation Research Board,
bus fatalities is also an exception to the sudden spike of fatal accidents
due to a decrease in operation hours for buses during the COVID-19 pandemic, as well as
social distancing measures and precautions advised and enforced by state legislature.
(https://www.ncbi.nlm.nih.gov/pmc/articles/PMC10107069/)

Christy Bieber, J.D., indicated that the top 5 most deadliest states to drive in are
Montana, South Carolina, New Mexico, Wyoming, and Texas based on data from the
National Highway Traffic Safety Administration (NHTSA). This seems to align with
our data for Pedestrian  Fatalities by State Population Density.
(https://www.forbes.com/advisor/legal/most-dangerous-states-for-drivers/) 

According to Alina Comoreanu, a Senior researcher at WalletHub, the top 5 states that 
had the most strictest enforcement on speeding and reckless driving are (in order) 
Delaware, Colorado, Arizona, New Mexico, and California. This seems to correlate
with our data for Pedestrian Fatalities by State Population Density.
(https://wallethub.com/edu/strictest-and-most-lenient-states-on-speeding/14211)

### Data Setup




```
##           State                            X  X2010  X2011  X2012  X2013  X2014
## 1 United States           Highway Fatalities 32,999 32,479 33,782 32,893 32,744
## 2 United States     Passenger Car Fatalities 12,491 12,014 12,361 12,037 11,947
## 3 United States               SUV Fatalities  3,942  3,884  3,885  3,831  3,800
## 4 United States      Pickup Truck Fatalities  4,486  4,270  4,343  4,175  4,249
## 5 United States               Van Fatalities  1,346  1,128  1,167  1,142  1,021
## 6 United States Other Light Truck Fatalities      8     20     23     38     33
##    X2015  X2016  X2017  X2018  X2019  X2020  X2021 totalFatalities
## 1 35,484 37,806 37,473 36,835 36,355 39,007 42,939         430,796
## 2 12,763 13,508 13,477 12,888 12,355 12,628 13,529         151,998
## 3  4,213  4,462  4,610  4,554  4,727  6,015  6,961          54,884
## 4  4,471  4,470  4,335  4,267  4,213  4,333  4,757          52,369
## 5  1,128  1,240  1,175  1,081  1,025    938  1,078          13,469
## 6     66    107     66     55     52      0      0             468
```

```
##     State                X                X2010              X2011          
##  Length:756         Length:756         Length:756         Length:756        
##  Class :character   Class :character   Class :character   Class :character  
##  Mode  :character   Mode  :character   Mode  :character   Mode  :character  
##     X2012              X2013              X2014              X2015          
##  Length:756         Length:756         Length:756         Length:756        
##  Class :character   Class :character   Class :character   Class :character  
##  Mode  :character   Mode  :character   Mode  :character   Mode  :character  
##     X2016              X2017              X2018              X2019          
##  Length:756         Length:756         Length:756         Length:756        
##  Class :character   Class :character   Class :character   Class :character  
##  Mode  :character   Mode  :character   Mode  :character   Mode  :character  
##     X2020              X2021           totalFatalities   
##  Length:756         Length:756         Length:756        
##  Class :character   Class :character   Class :character  
##  Mode  :character   Mode  :character   Mode  :character
```

```
##           State                            X  X2010  X2011  X2012  X2013  X2014
## 1 United States           Highway Fatalities 32,999 32,479 33,782 32,893 32,744
## 2 United States     Passenger Car Fatalities 12,491 12,014 12,361 12,037 11,947
## 3 United States               SUV Fatalities  3,942  3,884  3,885  3,831  3,800
## 4 United States      Pickup Truck Fatalities  4,486  4,270  4,343  4,175  4,249
## 5 United States               Van Fatalities  1,346  1,128  1,167  1,142  1,021
## 6 United States Other Light Truck Fatalities      8     20     23     38     33
##    X2015  X2016  X2017  X2018  X2019  X2020  X2021 totalFatalities
## 1 35,484 37,806 37,473 36,835 36,355 39,007 42,939         430,796
## 2 12,763 13,508 13,477 12,888 12,355 12,628 13,529         151,998
## 3  4,213  4,462  4,610  4,554  4,727  6,015  6,961          54,884
## 4  4,471  4,470  4,335  4,267  4,213  4,333  4,757          52,369
## 5  1,128  1,240  1,175  1,081  1,025    938  1,078          13,469
## 6     66    107     66     55     52      0      0             468
```

```
##     State               Y2010               Y2011               Y2012          
##  Length:53          Min.   :   564531   Min.   :   567491   Min.   :   576656  
##  Class :character   1st Qu.:  1829591   1st Qu.:  1840914   1st Qu.:  1853691  
##  Mode  :character   Median :  4348464   Median :  4370817   Median :  4387865  
##                     Mean   : 11742940   Mean   : 11827277   Mean   : 11913015  
##                     3rd Qu.:  6743009   3rd Qu.:  6827479   3rd Qu.:  6898599  
##                     Max.   :309327143   Max.   :311583481   Max.   :313877662  
##      Y2013               Y2014               Y2015          
##  Min.   :   582620   Min.   :   583159   Min.   :   586389  
##  1st Qu.:  1854768   1st Qu.:  1850569   1st Qu.:  1843332  
##  Median :  4406906   Median :  4416992   Median :  4429126  
##  Mean   : 11994584   Mean   : 12081274   Mean   : 12168891  
##  3rd Qu.:  6966252   3rd Qu.:  7057531   3rd Qu.:  7167287  
##  Max.   :316059947   Max.   :318386329   Max.   :320738994  
##      Y2016               Y2017               Y2018          
##  Min.   :   585243   Min.   :   579994   Min.   :   579054  
##  1st Qu.:  1832435   1st Qu.:  1818683   1st Qu.:  1805953  
##  Median :  4440306   Median :  4455590   Median :  4464273  
##  Mean   : 12255664   Mean   : 12331501   Mean   : 12393769  
##  3rd Qu.:  7299961   3rd Qu.:  7427951   3rd Qu.:  7526793  
##  Max.   :323071755   Max.   :325122128   Max.   :326838199  
##      Y2019               Y2020               Y2021          
##  Min.   :   580116   Min.   :   582328   Min.   :   578803  
##  1st Qu.:  1795263   1st Qu.:  1826913   1st Qu.:  1900923  
##  Median :  4472345   Median :  4477251   Median :  4509394  
##  Mean   : 12450065   Mean   : 12492973   Mean   : 12585869  
##  3rd Qu.:  7614024   3rd Qu.:  7693612   3rd Qu.:  7738692  
##  Max.   :328329953   Max.   :329484123   Max.   :331893745
```


```
##     State                 FatalityType Y2010 Y2011 Y2012 Y2013 Y2014 Y2015
## 1 alabama           Highway Fatalities   862   895   865   853   820   850
## 2 alabama     Passenger Car Fatalities   376   389   370   357   337   355
## 3 alabama               SUV Fatalities   125   112   112   137   116   111
## 4 alabama      Pickup Truck Fatalities   153   154   140   151   150   156
## 5 alabama               Van Fatalities    33    27    26    20    15    23
## 6 alabama Other Light Truck Fatalities     2     1     0     1     0     3
##   Y2016 Y2017 Y2018 Y2019 Y2020 Y2021 TotalFatalities
## 1 1,083   948   953   930   934   983          10,976
## 2   416   395   411   362   371   368           4,507
## 3   166   143   136   126   166   182           1,632
## 4   165   145   149   160   152   131           1,806
## 5    24    27    19    21    16    40             291
## 6     9     1     1     4     0     0              22
```

```
##     State           FatalityType           Y2010             Y2011        
##  Length:742         Length:742         Min.   :   0.00   Min.   :   0.00  
##  Class :character   Class :character   1st Qu.:   1.00   1st Qu.:   1.00  
##  Mode  :character   Mode  :character   Median :  13.00   Median :  13.00  
##                                        Mean   :  91.61   Mean   :  90.23  
##                                        3rd Qu.:  70.00   3rd Qu.:  70.25  
##                                        Max.   :3023.00   Max.   :3054.00  
##                                        NA's   :14        NA's   :14       
##      Y2012             Y2013             Y2014             Y2015        
##  Min.   :   0.00   Min.   :   0.00   Min.   :   0.00   Min.   :   0.00  
##  1st Qu.:   1.00   1st Qu.:   1.00   1st Qu.:   1.00   1st Qu.:   1.00  
##  Median :  13.00   Median :  13.00   Median :  13.00   Median :  13.50  
##  Mean   :  93.83   Mean   :  91.34   Mean   :  90.84   Mean   :  98.36  
##  3rd Qu.:  75.00   3rd Qu.:  71.50   3rd Qu.:  69.00   3rd Qu.:  75.00  
##  Max.   :3408.00   Max.   :3389.00   Max.   :3536.00   Max.   :3582.00  
##  NA's   :14        NA's   :14        NA's   :14        NA's   :14       
##      Y2016            Y2017             Y2018             Y2019       
##  Min.   :   0.0   Min.   :   0.00   Min.   :   0.00   Min.   :   0.0  
##  1st Qu.:   2.0   1st Qu.:   2.00   1st Qu.:   1.75   1st Qu.:   2.0  
##  Median :  17.0   Median :  15.00   Median :  15.00   Median :  14.0  
##  Mean   : 104.6   Mean   : 103.76   Mean   : 102.02   Mean   : 100.7  
##  3rd Qu.:  81.0   3rd Qu.:  79.25   3rd Qu.:  80.50   3rd Qu.:  78.0  
##  Max.   :3837.0   Max.   :3884.00   Max.   :3798.00   Max.   :3719.0  
##  NA's   :14       NA's   :14        NA's   :14        NA's   :14      
##      Y2020            Y2021         TotalFatalities  
##  Min.   :   0.0   Min.   :   0.00   Min.   :    0.0  
##  1st Qu.:   1.0   1st Qu.:   1.00   1st Qu.:   18.0  
##  Median :  16.0   Median :  17.00   Median :  174.0  
##  Mean   : 107.8   Mean   : 118.85   Mean   : 1194.0  
##  3rd Qu.:  79.0   3rd Qu.:  91.25   3rd Qu.:  920.2  
##  Max.   :3980.0   Max.   :4498.00   Max.   :43162.0  
##  NA's   :14       NA's   :14        NA's   :14
```

#### Plan of Data Exploration

Break down each fatality type and plot the data by state, observe similarities and differences between the states for each fatality type.

### Data Exploration


```
## Warning in left_join(state_map, states_year, by = "State"): Detected an unexpected many-to-many relationship between `x` and `y`.
## ℹ Row 1 of `x` matches multiple rows in `y`.
## ℹ Row 1 of `y` matches multiple rows in `x`.
## ℹ If a many-to-many relationship is expected, set `relationship =
##   "many-to-many"` to silence this warning.
```


```
## Warning: Removed 12 rows containing missing values (`position_stack()`).
```

<img src="ds202_final_report_files/figure-html/unnamed-chunk-4-1.png" width="672" /><img src="ds202_final_report_files/figure-html/unnamed-chunk-4-2.png" width="672" /><img src="ds202_final_report_files/figure-html/unnamed-chunk-4-3.png" width="672" />

```
## Warning: Removed 12 rows containing missing values (`position_stack()`).
```

<img src="ds202_final_report_files/figure-html/unnamed-chunk-4-4.png" width="672" /><img src="ds202_final_report_files/figure-html/unnamed-chunk-4-5.png" width="672" /><img src="ds202_final_report_files/figure-html/unnamed-chunk-4-6.png" width="672" />

```
## Warning: Removed 12 rows containing missing values (`position_stack()`).
```

<img src="ds202_final_report_files/figure-html/unnamed-chunk-4-7.png" width="672" /><img src="ds202_final_report_files/figure-html/unnamed-chunk-4-8.png" width="672" /><img src="ds202_final_report_files/figure-html/unnamed-chunk-4-9.png" width="672" />




```
## Warning: Removed 12 rows containing missing values (`position_stack()`).
```

<img src="ds202_final_report_files/figure-html/unnamed-chunk-5-1.png" width="672" /><img src="ds202_final_report_files/figure-html/unnamed-chunk-5-2.png" width="672" /><img src="ds202_final_report_files/figure-html/unnamed-chunk-5-3.png" width="672" />

```
## Warning: Removed 12 rows containing missing values (`position_stack()`).
```

<img src="ds202_final_report_files/figure-html/unnamed-chunk-5-4.png" width="672" /><img src="ds202_final_report_files/figure-html/unnamed-chunk-5-5.png" width="672" /><img src="ds202_final_report_files/figure-html/unnamed-chunk-5-6.png" width="672" />

```
## Warning: Removed 12 rows containing missing values (`position_stack()`).
```

<img src="ds202_final_report_files/figure-html/unnamed-chunk-5-7.png" width="672" /><img src="ds202_final_report_files/figure-html/unnamed-chunk-5-8.png" width="672" /><img src="ds202_final_report_files/figure-html/unnamed-chunk-5-9.png" width="672" />

```
## Warning: Removed 12 rows containing missing values (`position_stack()`).
```

<img src="ds202_final_report_files/figure-html/unnamed-chunk-5-10.png" width="672" /><img src="ds202_final_report_files/figure-html/unnamed-chunk-5-11.png" width="672" /><img src="ds202_final_report_files/figure-html/unnamed-chunk-5-12.png" width="672" />


```
## Warning in geom_col(space = 1): Ignoring unknown parameters: `space`
```

```
## Warning: Removed 12 rows containing missing values (`position_stack()`).
```

<img src="ds202_final_report_files/figure-html/unnamed-chunk-6-1.png" width="672" /><img src="ds202_final_report_files/figure-html/unnamed-chunk-6-2.png" width="672" /><img src="ds202_final_report_files/figure-html/unnamed-chunk-6-3.png" width="672" />

```
## Warning in geom_col(space = 1): Ignoring unknown parameters: `space`
## Removed 12 rows containing missing values (`position_stack()`).
```

<img src="ds202_final_report_files/figure-html/unnamed-chunk-6-4.png" width="672" /><img src="ds202_final_report_files/figure-html/unnamed-chunk-6-5.png" width="672" /><img src="ds202_final_report_files/figure-html/unnamed-chunk-6-6.png" width="672" />

```
## Warning in geom_col(space = 1): Ignoring unknown parameters: `space`
## Removed 12 rows containing missing values (`position_stack()`).
```

<img src="ds202_final_report_files/figure-html/unnamed-chunk-6-7.png" width="672" /><img src="ds202_final_report_files/figure-html/unnamed-chunk-6-8.png" width="672" /><img src="ds202_final_report_files/figure-html/unnamed-chunk-6-9.png" width="672" />



```
## Warning in left_join(., state_map2, by = "region"): Detected an unexpected many-to-many relationship between `x` and `y`.
## ℹ Row 1 of `x` matches multiple rows in `y`.
## ℹ Row 1 of `y` matches multiple rows in `x`.
## ℹ If a many-to-many relationship is expected, set `relationship =
##   "many-to-many"` to silence this warning.
```

```
##     State       FatalityType Y2010 Y2011 Y2012 Y2013 Y2014 Y2015 Y2016 Y2017
## 1 alabama Highway Fatalities   862   895   865   853   820   850  1083   948
## 2 alabama Highway Fatalities   862   895   865   853   820   850  1083   948
## 3 alabama Highway Fatalities   862   895   865   853   820   850  1083   948
## 4 alabama Highway Fatalities   862   895   865   853   820   850  1083   948
## 5 alabama Highway Fatalities   862   895   865   853   820   850  1083   948
## 6 alabama Highway Fatalities   862   895   865   853   820   850  1083   948
##   Y2018 Y2019 Y2020 Y2021 TotalFatalities  region      long      lat group
## 1   953   930   934   983           10976 alabama -87.46201 30.38968     1
## 2   953   930   934   983           10976 alabama -87.48493 30.37249     1
## 3   953   930   934   983           10976 alabama -87.52503 30.37249     1
## 4   953   930   934   983           10976 alabama -87.53076 30.33239     1
## 5   953   930   934   983           10976 alabama -87.57087 30.32665     1
## 6   953   930   934   983           10976 alabama -87.58806 30.32665     1
##   order subregion
## 1     1      <NA>
## 2     2      <NA>
## 3     3      <NA>
## 4     4      <NA>
## 5     5      <NA>
## 6     6      <NA>
```

<img src="ds202_final_report_files/figure-html/unnamed-chunk-7-1.png" width="672" /><img src="ds202_final_report_files/figure-html/unnamed-chunk-7-2.png" width="672" /><img src="ds202_final_report_files/figure-html/unnamed-chunk-7-3.png" width="672" /><img src="ds202_final_report_files/figure-html/unnamed-chunk-7-4.png" width="672" /><img src="ds202_final_report_files/figure-html/unnamed-chunk-7-5.png" width="672" /><img src="ds202_final_report_files/figure-html/unnamed-chunk-7-6.png" width="672" />

```
## Warning: Removed 12 rows containing missing values (`position_stack()`).
```

<img src="ds202_final_report_files/figure-html/unnamed-chunk-7-7.png" width="672" />

```
## Warning: Removed 12 rows containing missing values (`position_stack()`).
```

<img src="ds202_final_report_files/figure-html/unnamed-chunk-7-8.png" width="672" />

```
## Warning: Removed 12 rows containing missing values (`position_stack()`).
```

<img src="ds202_final_report_files/figure-html/unnamed-chunk-7-9.png" width="672" />


#### Results:

