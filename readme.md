
## Case 4 - R Script
```
path <- file.path("~", "Documents/Niagara University/Social Media Marketing - MKG 637IS/R Case 4/storeclustercombined.csv")
library(multcomp)
library(tidyverse)
mystoredata.df <-read.table(path,
                            header = TRUE,
                            sep = ",",
                            stringsAsFactors = TRUE)
dim(mystoredata.df)
aggregate(salesthisyear ~ segment, data=mystoredata.df, mean)
aggregate (salesthisyear ~ storeid, data=mystoredata.df, mean)
aggregate (salesthisyear ~ chainclass, data=mystoredata.df, mean)
store.aov.salesthisyear <- aov(salesthisyear ~ -1 + storeid, data=mystoredata.df)
anova(store.aov.salesthisyear)
glht(store.aov.salesthisyear)
par(mar=c(6,10,2,2))
plot (glht(store.aov.salesthisyear),
      xlab="Sales this Year",
      main="Store Sales (95% CI)")
segment.aov.salesthisyear <- aov(salesthisyear ~ -1 + segment, data=mystoredata.df)
anova(segment.aov.salesthisyear)
glht(segment.aov.salesthisyear)
par(mar=c(6,10,2,2))
plot (glht(segment.aov.salesthisyear),
      xlab="Sales this Year",
      main="Store Sales (95% CI)")
chainclass.aov.salesthisyear <- aov(salesthisyear ~ -1 + chainclass, data=mystoredata.df)
anova(chainclass.aov.salesthisyear)
glht(chainclass.aov.salesthisyear)
par(mar=c(6,10,2,2))
plot (glht(chainclass.aov.salesthisyear),
      xlab="Sales this Year",
      main="Store Sales (95% CI)")
t.test(salesthisyear ~ storeid, data=subset(mystoredata.df, chainclass == "bluecollar"))

path <- file.path("~", "Documents/Niagara University/Social Media Marketing - MKG 637IS/R Case 4/scannerdataset.csv")
myscannerdata.df <- read.table(path,
                               header = TRUE,
                               sep = ",",
                               stringsAsFactors=FALSE)
dim(myscannerdata.df)
model1 <- lm(UNITS ~ PR + FA + FAPLUS + FB + FC + DFLAG, data=myscannerdata.df)
summary(model1)

model2 <- lm(UNITS ~ FA + DFLAG, data=myscannerdata.df)
summary(model2)

## Output 
```
 > install.packages(c("multcomp", "tidyverse"))
also installing the dependencies ‘sys’, ‘sass’, ‘cachem’, ‘memoise’, ‘lifecycle’, ‘rappdirs’, ‘askpass’, ‘bslib’, ‘jquerylib’, ‘tinytex’, ‘assertthat’, ‘blob’, ‘cli’, ‘DBI’, ‘dplyr’, ‘vctrs’, ‘gargle’, ‘uuid’, ‘curl’, ‘ids’, ‘mime’, ‘openssl’, ‘timechange’, ‘rlang’, ‘fs’, ‘rmarkdown’, ‘selectr’, ‘dbplyr’, ‘dtplyr’, ‘googledrive’, ‘googlesheets4’, ‘httr’, ‘lubridate’, ‘modelr’, ‘reprex’, ‘rvest’, ‘xml2’

trying URL 'https://cran.rstudio.com/bin/macosx/contrib/4.1/sys_3.4.1.tgz'
Content type 'application/x-gzip' length 47312 bytes (46 KB)
==================================================
downloaded 46 KB

trying URL 'https://cran.rstudio.com/bin/macosx/contrib/4.1/sass_0.4.4.tgz'
Content type 'application/x-gzip' length 2391629 bytes (2.3 MB)
==================================================
downloaded 2.3 MB

trying URL 'https://cran.rstudio.com/bin/macosx/contrib/4.1/cachem_1.0.6.tgz'
Content type 'application/x-gzip' length 66261 bytes (64 KB)
==================================================
downloaded 64 KB

trying URL 'https://cran.rstudio.com/bin/macosx/contrib/4.1/memoise_2.0.1.tgz'
Content type 'application/x-gzip' length 48111 bytes (46 KB)
==================================================
downloaded 46 KB

trying URL 'https://cran.rstudio.com/bin/macosx/contrib/4.1/lifecycle_1.0.3.tgz'
Content type 'application/x-gzip' length 121579 bytes (118 KB)
==================================================
downloaded 118 KB

trying URL 'https://cran.rstudio.com/bin/macosx/contrib/4.1/rappdirs_0.3.3.tgz'
Content type 'application/x-gzip' length 45686 bytes (44 KB)
==================================================
downloaded 44 KB

trying URL 'https://cran.rstudio.com/bin/macosx/contrib/4.1/askpass_1.1.tgz'
Content type 'application/x-gzip' length 21566 bytes (21 KB)
==================================================
downloaded 21 KB

trying URL 'https://cran.rstudio.com/bin/macosx/contrib/4.1/bslib_0.4.1.tgz'
Content type 'application/x-gzip' length 4756460 bytes (4.5 MB)
==================================================
downloaded 4.5 MB

trying URL 'https://cran.rstudio.com/bin/macosx/contrib/4.1/jquerylib_0.1.4.tgz'
Content type 'application/x-gzip' length 525978 bytes (513 KB)
==================================================
downloaded 513 KB

trying URL 'https://cran.rstudio.com/bin/macosx/contrib/4.1/tinytex_0.42.tgz'
Content type 'application/x-gzip' length 133149 bytes (130 KB)
==================================================
downloaded 130 KB

trying URL 'https://cran.rstudio.com/bin/macosx/contrib/4.1/assertthat_0.2.1.tgz'
Content type 'application/x-gzip' length 52388 bytes (51 KB)
==================================================
downloaded 51 KB

trying URL 'https://cran.rstudio.com/bin/macosx/contrib/4.1/blob_1.2.3.tgz'
Content type 'application/x-gzip' length 46084 bytes (45 KB)
==================================================
downloaded 45 KB

trying URL 'https://cran.rstudio.com/bin/macosx/contrib/4.1/cli_3.4.1.tgz'
Content type 'application/x-gzip' length 1284268 bytes (1.2 MB)
==================================================
downloaded 1.2 MB

trying URL 'https://cran.rstudio.com/bin/macosx/contrib/4.1/DBI_1.1.3.tgz'
Content type 'application/x-gzip' length 745918 bytes (728 KB)
==================================================
downloaded 728 KB

trying URL 'https://cran.rstudio.com/bin/macosx/contrib/4.1/dplyr_1.0.10.tgz'
Content type 'application/x-gzip' length 1312335 bytes (1.3 MB)
==================================================
downloaded 1.3 MB

trying URL 'https://cran.rstudio.com/bin/macosx/contrib/4.1/vctrs_0.5.1.tgz'
Content type 'application/x-gzip' length 1821002 bytes (1.7 MB)
==================================================
downloaded 1.7 MB

trying URL 'https://cran.rstudio.com/bin/macosx/contrib/4.1/gargle_1.2.1.tgz'
Content type 'application/x-gzip' length 501768 bytes (490 KB)
==================================================
downloaded 490 KB

trying URL 'https://cran.rstudio.com/bin/macosx/contrib/4.1/uuid_1.1-0.tgz'
Content type 'application/x-gzip' length 69006 bytes (67 KB)
==================================================
downloaded 67 KB

trying URL 'https://cran.rstudio.com/bin/macosx/contrib/4.1/curl_4.3.3.tgz'
Content type 'application/x-gzip' length 738955 bytes (721 KB)
==================================================
downloaded 721 KB

trying URL 'https://cran.rstudio.com/bin/macosx/contrib/4.1/ids_1.0.1.tgz'
Content type 'application/x-gzip' length 120058 bytes (117 KB)
==================================================
downloaded 117 KB

trying URL 'https://cran.rstudio.com/bin/macosx/contrib/4.1/mime_0.12.tgz'
Content type 'application/x-gzip' length 34812 bytes (33 KB)
==================================================
downloaded 33 KB

trying URL 'https://cran.rstudio.com/bin/macosx/contrib/4.1/openssl_2.0.5.tgz'
Content type 'application/x-gzip' length 2880780 bytes (2.7 MB)
==================================================
downloaded 2.7 MB

trying URL 'https://cran.rstudio.com/bin/macosx/contrib/4.1/timechange_0.1.1.tgz'
Content type 'application/x-gzip' length 839779 bytes (820 KB)
==================================================
downloaded 820 KB

trying URL 'https://cran.rstudio.com/bin/macosx/contrib/4.1/rlang_1.0.6.tgz'
Content type 'application/x-gzip' length 1811149 bytes (1.7 MB)
==================================================
downloaded 1.7 MB

trying URL 'https://cran.rstudio.com/bin/macosx/contrib/4.1/fs_1.5.2.tgz'
Content type 'application/x-gzip' length 545943 bytes (533 KB)
==================================================
downloaded 533 KB

trying URL 'https://cran.rstudio.com/bin/macosx/contrib/4.1/rmarkdown_2.18.tgz'
Content type 'application/x-gzip' length 3653799 bytes (3.5 MB)
==================================================
downloaded 3.5 MB

trying URL 'https://cran.rstudio.com/bin/macosx/contrib/4.1/selectr_0.4-2.tgz'
Content type 'application/x-gzip' length 489583 bytes (478 KB)
==================================================
downloaded 478 KB

trying URL 'https://cran.rstudio.com/bin/macosx/contrib/4.1/dbplyr_2.2.1.tgz'
Content type 'application/x-gzip' length 971831 bytes (949 KB)
==================================================
downloaded 949 KB

trying URL 'https://cran.rstudio.com/bin/macosx/contrib/4.1/dtplyr_1.2.2.tgz'
Content type 'application/x-gzip' length 327460 bytes (319 KB)
==================================================
downloaded 319 KB

trying URL 'https://cran.rstudio.com/bin/macosx/contrib/4.1/googledrive_2.0.0.tgz'
Content type 'application/x-gzip' length 1864881 bytes (1.8 MB)
==================================================
downloaded 1.8 MB

trying URL 'https://cran.rstudio.com/bin/macosx/contrib/4.1/googlesheets4_1.0.1.tgz'
Content type 'application/x-gzip' length 489112 bytes (477 KB)
==================================================
downloaded 477 KB

trying URL 'https://cran.rstudio.com/bin/macosx/contrib/4.1/httr_1.4.4.tgz'
Content type 'application/x-gzip' length 503962 bytes (492 KB)
==================================================
downloaded 492 KB

trying URL 'https://cran.rstudio.com/bin/macosx/contrib/4.1/lubridate_1.9.0.tgz'
Content type 'application/x-gzip' length 974722 bytes (951 KB)
==================================================
downloaded 951 KB

trying URL 'https://cran.rstudio.com/bin/macosx/contrib/4.1/modelr_0.1.10.tgz'
Content type 'application/x-gzip' length 200474 bytes (195 KB)
==================================================
downloaded 195 KB

trying URL 'https://cran.rstudio.com/bin/macosx/contrib/4.1/reprex_2.0.2.tgz'
Content type 'application/x-gzip' length 493220 bytes (481 KB)
==================================================
downloaded 481 KB

trying URL 'https://cran.rstudio.com/bin/macosx/contrib/4.1/rvest_1.0.3.tgz'
Content type 'application/x-gzip' length 210976 bytes (206 KB)
==================================================
downloaded 206 KB

trying URL 'https://cran.rstudio.com/bin/macosx/contrib/4.1/xml2_1.3.3.tgz'
Content type 'application/x-gzip' length 2335634 bytes (2.2 MB)
==================================================
downloaded 2.2 MB

trying URL 'https://cran.rstudio.com/bin/macosx/contrib/4.1/multcomp_1.4-20.tgz'
Content type 'application/x-gzip' length 739120 bytes (721 KB)
==================================================
downloaded 721 KB

trying URL 'https://cran.rstudio.com/bin/macosx/contrib/4.1/tidyverse_1.3.2.tgz'
Content type 'application/x-gzip' length 420934 bytes (411 KB)
==================================================
downloaded 411 KB


The downloaded binary packages are in
	/var/folders/sb/f3jmlct16v73cr4zn9hd_4kw0000gn/T//RtmpY38iRB/downloaded_packages
> path <- file.path("~", "Documents/Niagara University/Social Media Marketing - MKG 637IS/R Case 4/storeclustercombined.csv")
> library(multcomp)
Loading required package: mvtnorm
Loading required package: survival
Loading required package: TH.data
Loading required package: MASS

Attaching package: ‘TH.data’

The following object is masked from ‘package:MASS’:

    geyser
```
> library(tidyverse)
── Attaching packages ─────────────────────────────────────────────────────────── tidyverse 1.3.2 ──
✔ ggplot2 3.3.5      ✔ purrr   0.3.4 
✔ tibble  3.1.6      ✔ dplyr   1.0.10
✔ tidyr   1.2.1      ✔ stringr 1.4.0 
✔ readr   2.1.2      ✔ forcats 0.5.1 
── Conflicts ────────────────────────────────────────────────────────────── tidyverse_conflicts() ──
✖ dplyr::filter() masks stats::filter()
✖ dplyr::lag()    masks stats::lag()
✖ dplyr::select() masks MASS::select()
```
> mystoredata.df <-read.table(path,
+                             header = TRUE,
+                             sep = ",",
+                             stringsAsFactors = TRUE)
```
> dim(mystoredata.df)
[1] 216   5
```
> aggregate(salesthisyear ~ segment, data=mystoredata.df, mean)
       segment salesthisyear
1     CONSUMER      9178.078
2 PROFESSIONAL      6040.267
3    SPECIALTY      3804.241
4        VALUE      6031.467
```
> aggregate (salesthisyear ~ storeid, data=mystoredata.df, mean)
      storeid salesthisyear
1 bluecollar1      5825.139
2 bluecollar2      8392.500
3    highend1      4149.306
4    highend2     10737.917
5   hispanic1      8163.167
6   hispanic2      4502.667
```
> aggregate (salesthisyear ~ chainclass, data=mystoredata.df, mean)
  chainclass salesthisyear
1 bluecollar      7108.819
2    highend      7443.611
3   hispanic      6332.917
```
> store.aov.salesthisyear <- aov(salesthisyear ~ -1 + storeid, data=mystoredata.df)
> anova(store.aov.salesthisyear)
Analysis of Variance Table

Response: salesthisyear
           Df     Sum Sq    Mean Sq F value    Pr(>F)    
storeid     6 1.1657e+10 1942783124  33.343 < 2.2e-16 ***
Residuals 210 1.2236e+10   58266032                      
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
> glht(store.aov.salesthisyear)

	 General Linear Hypotheses

Linear Hypotheses:
                        Estimate
storeidbluecollar1 == 0     5825
storeidbluecollar2 == 0     8392
storeidhighend1 == 0        4149
storeidhighend2 == 0       10738
storeidhispanic1 == 0       8163
storeidhispanic2 == 0       4503
```
> par(mar=c(6,10,2,2))
```
> plot (glht(store.aov.salesthisyear),
+       xlab="Sales this Year",
+       main="Store Sales (95% CI)")
```
> segment.aov.salesthisyear <- aov(salesthisyear ~ -1 + segment, data=mystoredata.df)
```
> anova(segment.aov.salesthisyear)
Analysis of Variance Table

Response: salesthisyear
           Df     Sum Sq    Mean Sq F value    Pr(>F)    
segment     4 1.1560e+10 2889897584  49.676 < 2.2e-16 ***
Residuals 212 1.2333e+10   58174411                      
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
> glht(segment.aov.salesthisyear)

	 General Linear Hypotheses

Linear Hypotheses:
                         Estimate
segmentCONSUMER == 0         9178
segmentPROFESSIONAL == 0     6040
segmentSPECIALTY == 0        3804
segmentVALUE == 0            6031
```
> par(mar=c(6,10,2,2))
```
> plot (glht(segment.aov.salesthisyear),
+       xlab="Sales this Year",
+       main="Store Sales (95% CI)")
```
> chainclass.aov.salesthisyear <- aov(salesthisyear ~ -1 + chainclass, data=mystoredata.df)
```
> anova(chainclass.aov.salesthisyear)
Analysis of Variance Table

Response: salesthisyear
            Df     Sum Sq    Mean Sq F value    Pr(>F)    
chainclass   3 1.0515e+10 3505163851  55.812 < 2.2e-16 ***
Residuals  213 1.3377e+10   62803163                      
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
> glht(chainclass.aov.salesthisyear)

	 General Linear Hypotheses

Linear Hypotheses:
                          Estimate
chainclassbluecollar == 0     7109
chainclasshighend == 0        7444
chainclasshispanic == 0       6333
```
> par(mar=c(6,10,2,2))
```
> plot (glht(chainclass.aov.salesthisyear),
+       xlab="Sales this Year",
+       main="Store Sales (95% CI)")
```
> t.test(salesthisyear ~ storeid, data=subset(mystoredata.df, chainclass == "hispanic"))

	Welch Two Sample t-test

data:  salesthisyear by storeid
t = 2.6151, df = 68.281, p-value = 0.01097
alternative hypothesis: true difference in means between group hispanic1 and group hispanic2 is not equal to 0
95 percent confidence interval:
  867.5693 6453.4307
sample estimates:
mean in group hispanic1 mean in group hispanic2 
               8163.167                4502.667 
```
> t.test(salesthisyear ~ storeid, data=subset(mystoredata.df, chainclass == "highend"))

	Welch Two Sample t-test

data:  salesthisyear by storeid
t = -2.8289, df = 39.152, p-value = 0.007328
alternative hypothesis: true difference in means between group highend1 and group highend2 is not equal to 0
95 percent confidence interval:
 -11298.891  -1878.331
sample estimates:
mean in group highend1 mean in group highend2 
              4149.306              10737.917 
```
> t.test(salesthisyear ~ storeid, data=subset(mystoredata.df, chainclass == "bluecollar"))

	Welch Two Sample t-test

data:  salesthisyear by storeid
t = -1.6829, df = 69.803, p-value = 0.09687
alternative hypothesis: true difference in means between group bluecollar1 and group bluecollar2 is not equal to 0
95 percent confidence interval:
 -5610.2232   475.5009
sample estimates:
mean in group bluecollar1 mean in group bluecollar2 
                 5825.139                  8392.500 
```
> path <- file.path("~", "Documents/Niagara University/Social Media Marketing - MKG 637IS/R Case 4/scannerdataset.csv")
```
> myscannerdata.df <- read.table(path,
+                                header = TRUE,
+                                sep = ",",
+                                stringsAsFactors=FALSE)
```
> path <- file.path("~", "Documents/Niagara University/Social Media Marketing - MKG 637IS/R Case 4/scannerdataset.csv")
```
> myscannerdata.df <- read.table(path,
+                                header = TRUE,
+                                sep = ",",
+                                stringsAsFactors=FALSE)
```
> dim(myscannerdata.df)
[1] 548573      7
```
> model1 <- lm(UNITS ~ PR + FA + FAPLUS + FB + FC + DFLAG, data=myscannerdata.df)
```
> summary(model1)

Call:
lm(formula = UNITS ~ PR + FA + FAPLUS + FB + FC + DFLAG, data = myscannerdata.df)

Residuals:
    Min      1Q  Median      3Q     Max 
 -44.93   -5.89   -3.89    1.11 1826.07 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)    
(Intercept)  6.89413    0.04031  171.03   <2e-16 ***
PR           3.26680    0.07875   41.48   <2e-16 ***
FA          20.46384    0.19645  104.17   <2e-16 ***
FAPLUS      12.04172    0.52707   22.85   <2e-16 ***
FB           8.69347    0.13912   62.49   <2e-16 ***
FC           9.27872    0.59817   15.51   <2e-16 ***
DFLAG       15.30602    0.08579  178.41   <2e-16 ***
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 24.06 on 548566 degrees of freedom
Multiple R-squared:  0.1028,	Adjusted R-squared:  0.1028 
F-statistic: 1.047e+04 on 6 and 548566 DF,  p-value: < 2.2e-16
```
> model2 <- lm(UNITS ~ FA + DFLAG, data=myscannerdata.df)
```
> summary(model2)

Call:
lm(formula = UNITS ~ FA + DFLAG, data = myscannerdata.df)

Residuals:
    Min      1Q  Median      3Q     Max 
 -45.07   -7.23   -4.23    0.77 1825.93 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)    
(Intercept)  8.22689    0.03645   225.7   <2e-16 ***
FA          21.40065    0.19252   111.2   <2e-16 ***
DFLAG       16.44100    0.08544   192.4   <2e-16 ***
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 24.25 on 548570 degrees of freedom
Multiple R-squared:  0.08821,	Adjusted R-squared:  0.08821 
F-statistic: 2.654e+04 on 2 and 548570 DF,  p-value: < 2.2e-16
