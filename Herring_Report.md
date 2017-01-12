# Raport - analiza rozmarów śledzi
Martin Berent  
`r format(Sys.time(), '%d %B, %Y')`  





<br>

### Dane
Atrybuty:

* **length:** długość złowionego śledzia [cm];
* **cfin1:** dostępność planktonu [zagęszczenie Calanus finmarchicus gat. 1];
* **cfin2:** dostępność planktonu [zagęszczenie Calanus finmarchicus gat. 2];
* **chel1:** *dostępność planktonu [zagęszczenie Calanus helgolandicus gat. 1];
* **chel2:** dostępność planktonu [zagęszczenie Calanus helgolandicus gat. 2];
* **lcop1:** dostępność planktonu [zagęszczenie widłonogów gat. 1];
* **lcop2:** dostępność planktonu [zagęszczenie widłonogów gat. 2];
* **fbar:** natężenie połowów w regionie [ułamek pozostawionego narybku];
* **recr:** roczny narybek [liczba śledzi];
* **cumf:** łączne roczne natężenie połowów w regionie [ułamek pozostawionego narybku];
* **totaln:** łączna liczba ryb złowionych w ramach połowu [liczba śledzi];
* **sst:** temperatura przy powierzchni wody [°C];
* **sal:** poziom zasolenia wody [Knudsen ppt];
* **xmonth:** miesiąc połowu [numer miesiąca];
* **nao:** oscylacja północnoatlantycka [mb].
<br><br>


```r
data <- read.csv("sledzie.csv", header = TRUE, sep = ",", na.strings = "?", nrows=52581)
data <- data[-1]
knitr::kable(head(data))
```



 length     cfin1     cfin2     chel1      chel2     lcop1      lcop2    fbar     recr        cumf     totaln        sst        sal   xmonth   nao
-------  --------  --------  --------  ---------  --------  ---------  ------  -------  ----------  ---------  ---------  ---------  -------  ----
   23.0   0.02778   0.27785   2.46875         NA   2.54787   26.35881   0.356   482831   0.3059879   267380.8   14.30693   35.51234        7   2.8
   22.5   0.02778   0.27785   2.46875   21.43548   2.54787   26.35881   0.356   482831   0.3059879   267380.8   14.30693   35.51234        7   2.8
   25.0   0.02778   0.27785   2.46875   21.43548   2.54787   26.35881   0.356   482831   0.3059879   267380.8   14.30693   35.51234        7   2.8
   25.5   0.02778   0.27785   2.46875   21.43548   2.54787   26.35881   0.356   482831   0.3059879   267380.8   14.30693   35.51234        7   2.8
   24.0   0.02778   0.27785   2.46875   21.43548   2.54787   26.35881   0.356   482831   0.3059879   267380.8   14.30693   35.51234        7   2.8
   22.0   0.02778   0.27785   2.46875   21.43548   2.54787         NA   0.356   482831   0.3059879   267380.8   14.30693   35.51234        7   2.8

<br>

### Podstawowe statystyki


```r
knitr::kable(summary(data))
```

         length         cfin1             cfin2             chel1            chel2            lcop1              lcop2             fbar             recr              cumf             totaln             sst             sal            xmonth            nao         
---  -------------  ----------------  ----------------  ---------------  ---------------  -----------------  ---------------  ---------------  ----------------  ----------------  ----------------  --------------  --------------  ---------------  -----------------
     Min.   :19.0   Min.   : 0.0000   Min.   : 0.0000   Min.   : 0.000   Min.   : 5.238   Min.   :  0.3074   Min.   : 7.849   Min.   :0.0680   Min.   : 140515   Min.   :0.06833   Min.   : 144137   Min.   :12.77   Min.   :35.40   Min.   : 1.000   Min.   :-4.89000 
     1st Qu.:24.0   1st Qu.: 0.0000   1st Qu.: 0.2778   1st Qu.: 2.469   1st Qu.:13.427   1st Qu.:  2.5479   1st Qu.:17.808   1st Qu.:0.2270   1st Qu.: 360061   1st Qu.:0.14809   1st Qu.: 306068   1st Qu.:13.60   1st Qu.:35.51   1st Qu.: 5.000   1st Qu.:-1.89000 
     Median :25.5   Median : 0.1111   Median : 0.7012   Median : 5.750   Median :21.673   Median :  7.0000   Median :24.859   Median :0.3320   Median : 421391   Median :0.23191   Median : 539558   Median :13.86   Median :35.51   Median : 8.000   Median : 0.20000 
     Mean   :25.3   Mean   : 0.4458   Mean   : 2.0248   Mean   :10.006   Mean   :21.221   Mean   : 12.8108   Mean   :28.419   Mean   :0.3303   Mean   : 520368   Mean   :0.22981   Mean   : 514979   Mean   :13.87   Mean   :35.51   Mean   : 7.258   Mean   :-0.09233 
     3rd Qu.:26.5   3rd Qu.: 0.3333   3rd Qu.: 1.7936   3rd Qu.:11.500   3rd Qu.:27.193   3rd Qu.: 21.2315   3rd Qu.:37.232   3rd Qu.:0.4560   3rd Qu.: 724151   3rd Qu.:0.29803   3rd Qu.: 730351   3rd Qu.:14.16   3rd Qu.:35.52   3rd Qu.: 9.000   3rd Qu.: 1.63000 
     Max.   :32.5   Max.   :37.6667   Max.   :19.3958   Max.   :75.000   Max.   :57.706   Max.   :115.5833   Max.   :68.736   Max.   :0.8490   Max.   :1565890   Max.   :0.39801   Max.   :1015595   Max.   :14.73   Max.   :35.61   Max.   :12.000   Max.   : 5.08000 
     NA             NA's   :1581      NA's   :1536      NA's   :1555     NA's   :1556     NA's   :1652       NA's   :1591     NA               NA                NA                NA                NA's   :1584    NA              NA               NA               
