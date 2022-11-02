World Happiness Data Analysis
================

Reading the data in and selecting only year 2018

``` r
data <- read.csv('whr2018.csv')
d18 <- data[data$Year=='2018',]
d18[1:10,]
```

    ##     Country.name Year Life.Ladder Log.GDP.per.capita Social.support
    ## 11   Afghanistan 2018    2.694303           7.494588      0.5075158
    ## 22       Albania 2018    5.004403           9.412399      0.6835917
    ## 29       Algeria 2018    5.043086           9.557952      0.7986513
    ## 46     Argentina 2018    5.792797           9.809972      0.8999116
    ## 59       Armenia 2018    5.062449           9.119424      0.8144490
    ## 71     Australia 2018    7.176993          10.721021      0.9401373
    ## 82       Austria 2018    7.396002          10.741893      0.9116681
    ## 95    Azerbaijan 2018    5.167995           9.678014      0.7812299
    ## 117   Bangladesh 2018    4.499217           8.220746      0.7055560
    ## 130      Belarus 2018    5.233770           9.778739      0.9045693
    ##     Healthy.life.expectancy.at.birth Freedom.to.make.life.choices   Generosity
    ## 11                              52.6                    0.3735355 -0.084887877
    ## 22                              68.7                    0.8242123  0.005384951
    ## 29                              65.9                    0.5833806 -0.172413006
    ## 46                              68.8                    0.8458947 -0.206936628
    ## 59                              66.9                    0.8076437 -0.149108693
    ## 71                              73.6                    0.9160281  0.137795404
    ## 82                              73.0                    0.9041120  0.051552333
    ## 95                              65.5                    0.7724493 -0.251795292
    ## 117                             64.3                    0.9014708 -0.038008336
    ## 130                             66.1                    0.6436024 -0.181864843
    ##     Perceptions.of.corruption Positive.affect Negative.affect
    ## 11                  0.9276057       0.4241253       0.4049044
    ## 22                  0.8991294       0.7132996       0.3189967
    ## 29                  0.7587041       0.5910429       0.2929456
    ## 46                  0.8552552       0.8203097       0.3205021
    ## 59                  0.6768264       0.5814877       0.4548403
    ## 71                  0.4046475       0.7590188       0.1874564
    ## 82                  0.5230606       0.7523504       0.2260588
    ## 95                  0.5612063       0.5925754       0.1913917
    ## 117                 0.7014212       0.5413447       0.3612378
    ## 130                 0.7184555       0.4503329       0.2357286
    ##     Confidence.in.national.government Democratic.Quality Delivery.Quality
    ## 11                          0.3646664                 NA               NA
    ## 22                          0.4353380                 NA               NA
    ## 29                                 NA                 NA               NA
    ## 46                          0.2613523                 NA               NA
    ## 59                          0.6708276                 NA               NA
    ## 71                          0.4688369                 NA               NA
    ## 82                          0.4886787                 NA               NA
    ## 95                          0.8343719                 NA               NA
    ## 117                         0.8316931                 NA               NA
    ## 130                         0.4212787                 NA               NA
    ##     Standard.deviation.of.ladder.by.country.year
    ## 11                                      1.408344
    ## 22                                      2.640531
    ## 29                                      1.973943
    ## 46                                      2.472559
    ## 59                                      2.102111
    ## 71                                      1.750283
    ## 82                                      1.551940
    ## 95                                      1.863302
    ## 117                                     2.159303
    ## 130                                     1.690107
    ##     Standard.deviation.Mean.of.ladder.by.country.year
    ## 11                                          0.5227117
    ## 22                                          0.5276415
    ## 29                                          0.3914157
    ## 46                                          0.4268333
    ## 59                                          0.4152360
    ## 71                                          0.2438741
    ## 82                                          0.2098350
    ## 95                                          0.3605464
    ## 117                                         0.4799286
    ## 130                                         0.3229235
    ##     GINI.index..World.Bank.estimate.
    ## 11                                NA
    ## 22                                NA
    ## 29                                NA
    ## 46                                NA
    ## 59                                NA
    ## 71                                NA
    ## 82                                NA
    ## 95                                NA
    ## 117                               NA
    ## 130                               NA
    ##     GINI.index..World.Bank.estimate...average.2000.16
    ## 11                                                 NA
    ## 22                                          0.3032500
    ## 29                                          0.2760000
    ## 46                                          0.4609375
    ## 59                                          0.3192500
    ## 71                                          0.3427500
    ## 82                                          0.3026923
    ## 95                                          0.2110000
    ## 117                                         0.3277500
    ## 130                                         0.2812941
    ##     gini.of.household.income.reported.in.Gallup..by.wp5.year
    ## 11                                                 0.2906813
    ## 22                                                 0.4561742
    ## 29                                                 0.6678719
    ## 46                                                 0.4053559
    ## 59                                                 0.4064035
    ## 71                                                 0.4298142
    ## 82                                                 0.2995044
    ## 95                                                 0.2604098
    ## 117                                                0.3676091
    ## 130                                                0.2934439
    ##     Most.people.can.be.trusted..Gallup
    ## 11                                  NA
    ## 22                                  NA
    ## 29                                  NA
    ## 46                                  NA
    ## 59                                  NA
    ## 71                                  NA
    ## 82                                  NA
    ## 95                                  NA
    ## 117                                 NA
    ## 130                                 NA
    ##     Most.people.can.be.trusted..WVS.round.1981.1984
    ## 11                                               NA
    ## 22                                               NA
    ## 29                                               NA
    ## 46                                        0.2700733
    ## 59                                               NA
    ## 71                                        0.4781494
    ## 82                                               NA
    ## 95                                               NA
    ## 117                                              NA
    ## 130                                              NA
    ##     Most.people.can.be.trusted..WVS.round.1989.1993
    ## 11                                               NA
    ## 22                                               NA
    ## 29                                               NA
    ## 46                                        0.2235529
    ## 59                                               NA
    ## 71                                               NA
    ## 82                                               NA
    ## 95                                               NA
    ## 117                                              NA
    ## 130                                       0.2502463
    ##     Most.people.can.be.trusted..WVS.round.1994.1998
    ## 11                                               NA
    ## 22                                        0.2432432
    ## 29                                               NA
    ## 46                                        0.1708436
    ## 59                                        0.2350000
    ## 71                                        0.3944921
    ## 82                                               NA
    ## 95                                        0.1943057
    ## 117                                       0.2045902
    ## 130                                       0.2299235
    ##     Most.people.can.be.trusted..WVS.round.1999.2004
    ## 11                                               NA
    ## 22                                        0.2320000
    ## 29                                        0.1076443
    ## 46                                        0.1501535
    ## 59                                               NA
    ## 71                                               NA
    ## 82                                               NA
    ## 95                                               NA
    ## 117                                       0.2326667
    ## 130                                              NA
    ##     Most.people.can.be.trusted..WVS.round.2005.2009
    ## 11                                               NA
    ## 22                                               NA
    ## 29                                               NA
    ## 46                                        0.1740575
    ## 59                                               NA
    ## 71                                        0.4613790
    ## 82                                               NA
    ## 95                                               NA
    ## 117                                              NA
    ## 130                                              NA
    ##     Most.people.can.be.trusted..WVS.round.2010.2014
    ## 11                                               NA
    ## 22                                               NA
    ## 29                                        0.1792863
    ## 46                                        0.1935307
    ## 59                                        0.1091358
    ## 71                                        0.5181401
    ## 82                                               NA
    ## 95                                        0.1479329
    ## 117                                              NA
    ## 130                                       0.3290649

Remove year and some other columns

``` r
d18 <- d18[-2] #year
d18 <- d18[1:11]
d18 <- d18[-9]
d18 <- d18[-9]
d18 = na.omit(d18) 
d18[1:10,]
```

    ##     Country.name Life.Ladder Log.GDP.per.capita Social.support
    ## 11   Afghanistan    2.694303           7.494588      0.5075158
    ## 22       Albania    5.004403           9.412399      0.6835917
    ## 46     Argentina    5.792797           9.809972      0.8999116
    ## 59       Armenia    5.062449           9.119424      0.8144490
    ## 71     Australia    7.176993          10.721021      0.9401373
    ## 82       Austria    7.396002          10.741893      0.9116681
    ## 95    Azerbaijan    5.167995           9.678014      0.7812299
    ## 117   Bangladesh    4.499217           8.220746      0.7055560
    ## 130      Belarus    5.233770           9.778739      0.9045693
    ## 142      Belgium    6.892172          10.672445      0.9298155
    ##     Healthy.life.expectancy.at.birth Freedom.to.make.life.choices   Generosity
    ## 11                              52.6                    0.3735355 -0.084887877
    ## 22                              68.7                    0.8242123  0.005384951
    ## 46                              68.8                    0.8458947 -0.206936628
    ## 59                              66.9                    0.8076437 -0.149108693
    ## 71                              73.6                    0.9160281  0.137795404
    ## 82                              73.0                    0.9041120  0.051552333
    ## 95                              65.5                    0.7724493 -0.251795292
    ## 117                             64.3                    0.9014708 -0.038008336
    ## 130                             66.1                    0.6436024 -0.181864843
    ## 142                             72.0                    0.8083866 -0.127278343
    ##     Perceptions.of.corruption Confidence.in.national.government
    ## 11                  0.9276057                         0.3646664
    ## 22                  0.8991294                         0.4353380
    ## 46                  0.8552552                         0.2613523
    ## 59                  0.6768264                         0.6708276
    ## 71                  0.4046475                         0.4688369
    ## 82                  0.5230606                         0.4886787
    ## 95                  0.5612063                         0.8343719
    ## 117                 0.7014212                         0.8316931
    ## 130                 0.7184555                         0.4212787
    ## 142                 0.6304118                         0.4419445

Scale variables between 0 and 10

``` r
d18[5] <- d18[5]/10
d18[4] <- d18[4]*10
d18[6] <- d18[6]*10
d18[7] <- d18[7]*10
d18[8] <- d18[8]*10
d18[9] <- d18[9]*10
d18[1:10,]
```

    ##     Country.name Life.Ladder Log.GDP.per.capita Social.support
    ## 11   Afghanistan    2.694303           7.494588       5.075158
    ## 22       Albania    5.004403           9.412399       6.835917
    ## 46     Argentina    5.792797           9.809972       8.999116
    ## 59       Armenia    5.062449           9.119424       8.144490
    ## 71     Australia    7.176993          10.721021       9.401373
    ## 82       Austria    7.396002          10.741893       9.116681
    ## 95    Azerbaijan    5.167995           9.678014       7.812299
    ## 117   Bangladesh    4.499217           8.220746       7.055560
    ## 130      Belarus    5.233770           9.778739       9.045693
    ## 142      Belgium    6.892172          10.672445       9.298155
    ##     Healthy.life.expectancy.at.birth Freedom.to.make.life.choices  Generosity
    ## 11                              5.26                     3.735355 -0.84887877
    ## 22                              6.87                     8.242123  0.05384951
    ## 46                              6.88                     8.458947 -2.06936628
    ## 59                              6.69                     8.076437 -1.49108693
    ## 71                              7.36                     9.160281  1.37795404
    ## 82                              7.30                     9.041120  0.51552333
    ## 95                              6.55                     7.724493 -2.51795292
    ## 117                             6.43                     9.014708 -0.38008336
    ## 130                             6.61                     6.436024 -1.81864843
    ## 142                             7.20                     8.083866 -1.27278343
    ##     Perceptions.of.corruption Confidence.in.national.government
    ## 11                   9.276057                          3.646664
    ## 22                   8.991294                          4.353380
    ## 46                   8.552552                          2.613523
    ## 59                   6.768264                          6.708276
    ## 71                   4.046475                          4.688369
    ## 82                   5.230606                          4.886787
    ## 95                   5.612063                          8.343719
    ## 117                  7.014212                          8.316931
    ## 130                  7.184555                          4.212787
    ## 142                  6.304118                          4.419445

``` r
sapply(d18, sd, na.rm = TRUE)
```

    ## Warning in var(if (is.vector(x) || is.factor(x)) x else as.double(x), na.rm =
    ## na.rm): NAs introduced by coercion

    ##                      Country.name                       Life.Ladder 
    ##                                NA                         1.1184826 
    ##                Log.GDP.per.capita                    Social.support 
    ##                         1.1891960                         1.1780494 
    ##  Healthy.life.expectancy.at.birth      Freedom.to.make.life.choices 
    ##                         0.6844595                         1.1812740 
    ##                        Generosity         Perceptions.of.corruption 
    ##                         1.5637734                         1.8658583 
    ## Confidence.in.national.government 
    ##                         2.0017211

``` r
summary(d18)
```

    ##  Country.name        Life.Ladder    Log.GDP.per.capita Social.support 
    ##  Length:113         Min.   :2.694   Min.   : 6.630     Min.   :5.035  
    ##  Class :character   1st Qu.:4.769   1st Qu.: 8.236     1st Qu.:7.385  
    ##  Mode  :character   Median :5.513   Median : 9.503     Median :8.470  
    ##                     Mean   :5.555   Mean   : 9.273     Mean   :8.133  
    ##                     3rd Qu.:6.276   3rd Qu.:10.236     3rd Qu.:9.098  
    ##                     Max.   :7.858   Max.   :11.454     Max.   :9.660  
    ##  Healthy.life.expectancy.at.birth Freedom.to.make.life.choices
    ##  Min.   :4.820                    Min.   :3.735               
    ##  1st Qu.:5.900                    1st Qu.:7.191               
    ##  Median :6.650                    Median :7.971               
    ##  Mean   :6.467                    Mean   :7.827               
    ##  3rd Qu.:6.960                    3rd Qu.:8.745               
    ##  Max.   :7.500                    Max.   :9.699               
    ##    Generosity      Perceptions.of.corruption Confidence.in.national.government
    ##  Min.   :-3.3638   Min.   :1.506             Min.   :0.7971                   
    ##  1st Qu.:-1.3174   1st Qu.:7.034             1st Qu.:3.2766                   
    ##  Median :-0.3696   Median :7.988             Median :4.7367                   
    ##  Mean   :-0.2359   Mean   :7.372             Mean   :4.9303                   
    ##  3rd Qu.: 0.6957   3rd Qu.:8.553             3rd Qu.:6.2226                   
    ##  Max.   : 4.9938   Max.   :9.520             Max.   :9.8812

rename cols

``` r
cols <- c("Country","Score", "Log GDP", "Social support", "Life expectancy", "Freedom", "Generosity", "Corruption", "Trust")
(length(cols))
```

    ## [1] 9

``` r
colnames(d18)[1] <- cols[1]
colnames(d18)[2] <- cols[2]
colnames(d18)[3] <- cols[3]
colnames(d18)[4] <- cols[4]
colnames(d18)[5] <- cols[5]
colnames(d18)[6] <- cols[6]
colnames(d18)[7] <- cols[7]
colnames(d18)[8] <- cols[8]
colnames(d18)[9] <- cols[9]
rownames(d18) <- d18[,1]
non <- d18[-1]
d18[1:10,]
```

    ##                 Country    Score   Log GDP Social support Life expectancy
    ## Afghanistan Afghanistan 2.694303  7.494588       5.075158            5.26
    ## Albania         Albania 5.004403  9.412399       6.835917            6.87
    ## Argentina     Argentina 5.792797  9.809972       8.999116            6.88
    ## Armenia         Armenia 5.062449  9.119424       8.144490            6.69
    ## Australia     Australia 7.176993 10.721021       9.401373            7.36
    ## Austria         Austria 7.396002 10.741893       9.116681            7.30
    ## Azerbaijan   Azerbaijan 5.167995  9.678014       7.812299            6.55
    ## Bangladesh   Bangladesh 4.499217  8.220746       7.055560            6.43
    ## Belarus         Belarus 5.233770  9.778739       9.045693            6.61
    ## Belgium         Belgium 6.892172 10.672445       9.298155            7.20
    ##              Freedom  Generosity Corruption    Trust
    ## Afghanistan 3.735355 -0.84887877   9.276057 3.646664
    ## Albania     8.242123  0.05384951   8.991294 4.353380
    ## Argentina   8.458947 -2.06936628   8.552552 2.613523
    ## Armenia     8.076437 -1.49108693   6.768264 6.708276
    ## Australia   9.160281  1.37795404   4.046475 4.688369
    ## Austria     9.041120  0.51552333   5.230606 4.886787
    ## Azerbaijan  7.724493 -2.51795292   5.612063 8.343719
    ## Bangladesh  9.014708 -0.38008336   7.014212 8.316931
    ## Belarus     6.436024 -1.81864843   7.184555 4.212787
    ## Belgium     8.083866 -1.27278343   6.304118 4.419445

``` r
ggpairs(non,columns=2:8)
```

![](project_files/figure-gfm/unnamed-chunk-7-1.png)<!-- -->

applying PCA

``` r
pca <- princomp(non)
pca
```

    ## Call:
    ## princomp(x = non)
    ## 
    ## Standard deviations:
    ##    Comp.1    Comp.2    Comp.3    Comp.4    Comp.5    Comp.6    Comp.7    Comp.8 
    ## 2.5464113 2.2773226 1.2601305 1.1486134 0.7491397 0.5105046 0.4770006 0.2886337 
    ## 
    ##  8  variables and  113 observations.

``` r
pca$loadings
```

    ## 
    ## Loadings:
    ##                 Comp.1 Comp.2 Comp.3 Comp.4 Comp.5 Comp.6 Comp.7 Comp.8
    ## Score                   0.427  0.148                0.635  0.608       
    ## Log GDP                 0.471         0.141 -0.465  0.267 -0.554 -0.405
    ## Social support          0.444  0.147  0.307 -0.250 -0.697  0.370       
    ## Life expectancy         0.262               -0.144        -0.284  0.906
    ## Freedom          0.290  0.191         0.483  0.735        -0.298       
    ## Generosity       0.364 -0.246  0.876 -0.119 -0.145                     
    ## Corruption      -0.571 -0.352  0.213  0.676 -0.128  0.169              
    ## Trust            0.669 -0.331 -0.362  0.413 -0.344         0.112       
    ## 
    ##                Comp.1 Comp.2 Comp.3 Comp.4 Comp.5 Comp.6 Comp.7 Comp.8
    ## SS loadings     1.000  1.000  1.000  1.000  1.000  1.000  1.000  1.000
    ## Proportion Var  0.125  0.125  0.125  0.125  0.125  0.125  0.125  0.125
    ## Cumulative Var  0.125  0.250  0.375  0.500  0.625  0.750  0.875  1.000

``` r
summary(pca)
```

    ## Importance of components:
    ##                           Comp.1    Comp.2    Comp.3     Comp.4     Comp.5
    ## Standard deviation     2.5464113 2.2773226 1.2601305 1.14861344 0.74913967
    ## Proportion of Variance 0.4127359 0.3301142 0.1010756 0.08397749 0.03572241
    ## Cumulative Proportion  0.4127359 0.7428501 0.8439257 0.92790315 0.96362556
    ##                            Comp.6     Comp.7      Comp.8
    ## Standard deviation     0.51050459 0.47700058 0.288633678
    ## Proportion of Variance 0.01658878 0.01448281 0.005302847
    ## Cumulative Proportion  0.98021434 0.99469715 1.000000000

scree

``` r
prop <- c(0.4127359, 0.3301142, 0.1010756, 0.08397749, 0.03572241, 0.01658878, 0.01448281, 0.005302847)
nam <- c("Comp1", "Comp2", "Comp3", "Comp4", "Comp5", "Comp6", "Comp7", "Comp8")

vars <- pca$sdev^2
var_prop <- vars / sum(vars)
var_prop_cum <- cumsum(var_prop)

par(mfrow=c(1,2))
plot(pca, las = 2, main = "Scree plot")
plot(var_prop_cum, type = "b", pch = 21, lty = 3, bg = "skyblue", cex = 1.5,
     ylim = c(0, 1), xlab = "Principal component",
     ylab = "Cumulative proportion of variance explained", main = "Cumulative explained variance")
```

![](project_files/figure-gfm/unnamed-chunk-10-1.png)<!-- -->

``` r
biplot(pca)
```

![](project_files/figure-gfm/unnamed-chunk-11-1.png)<!-- -->

triplot

``` r
#rglwidget()
plot3d(pca$scores[,1:3]) 
text3d(pca$scores[,1:3], texts=d18[,1])
text3d(4*pca$loadings[,1:3], texts=rownames(pca$loadings), col="red")
coords <- NULL
for (i in 1:nrow(pca$loadings)) {
  coords <- rbind(coords, rbind(c(0,0,0),3*pca$loadings[i,1:3]))}
lines3d(coords, col="red", lwd=2)
```

K-means

``` r
km <- kmeans(pca$scores[,1:3], 6, iter.max = 10, nstart = 1)
km
```

    ## K-means clustering with 6 clusters of sizes 26, 28, 14, 11, 27, 7
    ## 
    ## Cluster means:
    ##       Comp.1    Comp.2     Comp.3
    ## 1 -0.7750669  1.263094 -0.1580307
    ## 2 -0.2364489 -2.464778 -0.1498678
    ## 3  3.9932969  3.309964  0.2571632
    ## 4  2.6265381 -2.052442 -1.7519228
    ## 5 -2.8456577  1.054084  0.1886790
    ## 6  2.6867132 -2.292795  2.6973757
    ## 
    ## Clustering vector:
    ##            Afghanistan                Albania              Argentina 
    ##                      2                      2                      5 
    ##                Armenia              Australia                Austria 
    ##                      4                      3                      3 
    ##             Azerbaijan             Bangladesh                Belarus 
    ##                      4                      4                      1 
    ##                Belgium                  Benin                Bolivia 
    ##                      1                      2                      1 
    ## Bosnia and Herzegovina               Botswana                 Brazil 
    ##                      5                      4                      5 
    ##               Bulgaria           Burkina Faso               Cameroon 
    ##                      5                      2                      2 
    ##                 Canada                   Chad                  Chile 
    ##                      3                      2                      1 
    ##               Colombia                Comoros    Congo (Brazzaville) 
    ##                      5                      2                      2 
    ##             Costa Rica                Croatia         Czech Republic 
    ##                      1                      5                      1 
    ##                Denmark     Dominican Republic                Ecuador 
    ##                      3                      1                      1 
    ##            El Salvador                Estonia               Ethiopia 
    ##                      1                      1                      4 
    ##                Finland                 France                  Gabon 
    ##                      3                      1                      5 
    ##                Georgia                Germany                 Greece 
    ##                      5                      3                      5 
    ##              Guatemala                 Guinea                  Haiti 
    ##                      1                      2                      6 
    ##               Honduras                  India              Indonesia 
    ##                      1                      4                      6 
    ##                   Iran                Ireland                 Israel 
    ##                      2                      3                      1 
    ##                  Italy            Ivory Coast                  Japan 
    ##                      5                      2                      1 
    ##             Kazakhstan                  Kenya             Kyrgyzstan 
    ##                      1                      6                      6 
    ##                 Latvia                Lebanon                Liberia 
    ##                      5                      5                      2 
    ##              Lithuania             Luxembourg              Macedonia 
    ##                      5                      3                      5 
    ##             Madagascar                 Malawi               Malaysia 
    ##                      2                      2                      2 
    ##                   Mali             Mauritania              Mauritius 
    ##                      2                      5                      1 
    ##                 Mexico                Moldova               Mongolia 
    ##                      5                      5                      5 
    ##             Montenegro             Mozambique                Myanmar 
    ##                      1                      4                      6 
    ##                Namibia                  Nepal            Netherlands 
    ##                      2                      2                      3 
    ##            New Zealand              Nicaragua                  Niger 
    ##                      3                      1                      4 
    ##                Nigeria                 Norway               Pakistan 
    ##                      2                      3                      2 
    ##                 Panama                   Peru            Philippines 
    ##                      5                      5                      4 
    ##               Portugal                Romania                 Russia 
    ##                      1                      5                      1 
    ##                 Rwanda                Senegal                 Serbia 
    ##                      4                      2                      1 
    ##           Sierra Leone               Slovakia               Slovenia 
    ##                      2                      5                      5 
    ##           South Africa            South Korea                  Spain 
    ##                      2                      1                      5 
    ##              Sri Lanka                 Sweden            Switzerland 
    ##                      2                      3                      3 
    ##               Tanzania               Thailand                   Togo 
    ##                      4                      6                      2 
    ##                Tunisia                 Turkey                 Uganda 
    ##                      5                      1                      2 
    ##                Ukraine         United Kingdom          United States 
    ##                      5                      3                      1 
    ##                Uruguay             Uzbekistan              Venezuela 
    ##                      1                      6                      5 
    ##                 Zambia               Zimbabwe 
    ##                      2                      2 
    ## 
    ## Within cluster sum of squares by cluster:
    ## [1] 58.59027 81.97980 34.82521 59.95363 62.14067 49.25437
    ##  (between_SS / total_SS =  76.9 %)
    ## 
    ## Available components:
    ## 
    ## [1] "cluster"      "centers"      "totss"        "withinss"     "tot.withinss"
    ## [6] "betweenss"    "size"         "iter"         "ifault"

``` r
library(rworldmap)
```

    ## Loading required package: sp

    ## ### Welcome to rworldmap ###

    ## For a short introduction type :   vignette('rworldmap')

``` r
library(sp)

#create a map-shaped window
#mapDevice('x11')
#join to a coarse resolution map
#spdf <- joinCountryData2Map(km$cluster, joinCode="NAME", nameJoinColumn="country")

#mapCountryData(spdf, nameColumnToPlot="value", catMethod="fixedWidth")
```

``` r
library(RColorBrewer)
```

    ## Warning: package 'RColorBrewer' was built under R version 4.0.5

``` r
library(maptools)
```

    ## Checking rgeos availability: TRUE
    ## Please note that 'maptools' will be retired during 2023,
    ## plan transition at your earliest convenience;
    ## some functionality will be moved to 'sp'.

``` r
library(imputeTS)
```

    ## Registered S3 method overwritten by 'quantmod':
    ##   method            from
    ##   as.zoo.data.frame zoo

``` r
clusters <- data.frame(km$cluster)

data(wrld_simpl)
pal <- colorRampPalette(brewer.pal(7, 'Set2'))(7)#(length(7))#km$cluster))
pal <- pal[clusters[,1]]#findInterval(km$cluster, sort(unique(km$cluster))))]

col <- rep(grey(0.8), length(wrld_simpl@data$NAME))
col[na.replace(match(rownames(clusters), wrld_simpl@data$NAME),0)] <- pal
```

    ## Warning: na.replace will be replaced by na_replace.
    ##     Functionality stays the same.
    ##     The new function name better fits modern R code style guidelines.
    ##     Please adjust your code accordingly.

    ## Warning in col[na.replace(match(rownames(clusters), wrld_simpl@data$NAME), :
    ## number of items to replace is not a multiple of replacement length

``` r
plot(wrld_simpl, col = col)
```

![](project_files/figure-gfm/unnamed-chunk-15-1.png)<!-- -->

``` r
pal <- colorRampPalette(brewer.pal(7, 'Set3'))(7)
clusters['country'] <- rownames(clusters)
#join data to a map to create a spatialPolygonsDataFrame
sPDF <- joinCountryData2Map(clusters, joinCode='NAME', nameJoinColumn='country')
```

    ## 113 codes from your data successfully matched countries in the map
    ## 0 codes from your data failed to match with a country code in the map
    ## 130 codes from the map weren't represented in your data

``` r
#default map (see rworldmap documentation for options e.g. catMethod, numCats, colourPalette, mapRegion)
#missingCountryCol used for NA and countries not in the join file
mapCountryData(sPDF, nameColumnToPlot='km.cluster', missingCountryCol='grey', colourPalette = pal, catMethod = 'categorical', mapTitle = 'Happiness clusters of the world')
```

    ## Warning in rwmGetColours(colourPalette, numColours): 7 colours specified and 6
    ## required, using interpolation to calculate colours

![](project_files/figure-gfm/unnamed-chunk-16-1.png)<!-- -->
