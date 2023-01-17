---
title: "Lab 02 - Plastic waste"
author: "Heather Hawkins"
date: "01/17/23"
output:
  html_document:
    keep_md: yes
---

## Load packages and data


```r
library(tidyverse) 
```


```r
plastic_waste <- read_csv("data/plastic-waste.csv")
```
## Exercises

### Exercise 1

Remove this text, and add your answer for Exercise 1 here.


```r
ggplot(data = plastic_waste, aes(x = plastic_waste_per_cap)) +
  geom_histogram(binwidth = 0.2)
```

```
## Warning: Removed 51 rows containing non-finite values (`stat_bin()`).
```

![](lab-02_files/figure-html/plot-plastic_waste-1.png)<!-- -->


```r
plastic_waste %>%
  filter(plastic_waste_per_cap > 3.5)
```

```
## # A tibble: 1 × 10
##   code  entity     conti…¹  year gdp_p…² plast…³ misma…⁴ misma…⁵ coast…⁶ total…⁷
##   <chr> <chr>      <chr>   <dbl>   <dbl>   <dbl>   <dbl>   <dbl>   <dbl>   <dbl>
## 1 TTO   Trinidad … North …  2010  31261.     3.6    0.19   94066 1358433 1341465
## # … with abbreviated variable names ¹​continent, ²​gdp_per_cap,
## #   ³​plastic_waste_per_cap, ⁴​mismanaged_plastic_waste_per_cap,
## #   ⁵​mismanaged_plastic_waste, ⁶​coastal_pop, ⁷​total_pop
```

This is not surprising since Trinidad and Tobago have a lack of waste segregation among households alongside inefficient waste management systems. 



```r
ggplot(data = plastic_waste,
       aes(x = plastic_waste_per_cap)) +
  geom_density()
```

```
## Warning: Removed 51 rows containing non-finite values (`stat_density()`).
```

![](lab-02_files/figure-html/plastic-waste-continent-1.png)<!-- -->

```r
ggplot(data = plastic_waste, 
       mapping = aes(x = plastic_waste_per_cap, 
                     color = continent)) +
  geom_density()
```

```
## Warning: Removed 51 rows containing non-finite values (`stat_density()`).
```

![](lab-02_files/figure-html/plastic-waste-continent-2.png)<!-- -->

```r
ggplot(data = plastic_waste, 
       mapping = aes(x = plastic_waste_per_cap, 
                     color = continent, 
                     fill = continent)) +
  geom_density()
```

```
## Warning: Removed 51 rows containing non-finite values (`stat_density()`).
```

![](lab-02_files/figure-html/plastic-waste-continent-3.png)<!-- -->

```r
ggplot(data = plastic_waste, 
       mapping = aes(x = plastic_waste_per_cap, 
                     color = continent, 
                     fill = continent)) +
  geom_density(alpha = 0.7)
```

```
## Warning: Removed 51 rows containing non-finite values (`stat_density()`).
```

![](lab-02_files/figure-html/plastic-waste-continent-4.png)<!-- -->

### Exercise 2.1


```r
ggplot(data = plastic_waste, 
       mapping = aes(x = plastic_waste_per_cap, 
                     color = continent, 
                     fill = continent)) +
  geom_density(alpha = 0.2)
```

```
## Warning: Removed 51 rows containing non-finite values (`stat_density()`).
```

![](lab-02_files/figure-html/plastic-waste-density-1.png)<!-- -->

### Exercise 2.2

By defining the color and fill for continent through mapping the aesthetics, we can set individual colors and color fills for each continent. By defining the alpha level through the plotting gem, every continent's characteristic can be changed. Plotting Gem affects every data point while mapping aesthesics separates each category. 

### Exercise 3.1
(OG boxplot)

Blox plots show us where most of the data is, as well as individual outliers that occur.


```r
ggplot(data = plastic_waste, 
       mapping = aes(x = continent, 
                     y = plastic_waste_per_cap)) +
  geom_boxplot(alpha = 0.7)
```

```
## Warning: Removed 51 rows containing non-finite values (`stat_boxplot()`).
```

![](lab-02_files/figure-html/plastic-waste-boxplot-1.png)<!-- -->

(Violin Plot)

The violin plot show us the density and distribution of data points in waves, we can see exactly where it is most concentrated and where it is not.


```r
ggplot(data = plastic_waste, 
       mapping = aes(x = continent, 
                     y = plastic_waste_per_cap)) +
  geom_violin()
```

```
## Warning: Removed 51 rows containing non-finite values (`stat_ydensity()`).
```

![](lab-02_files/figure-html/plastic-waste-violin-1.png)<!-- -->

### Exercise 4.1

Remove this text, and add your answer for Exercise 5 here.


```r
# insert code here
```

### Exercise 4.2

Remove this text, and add your answer for Exercise 6 here.


```r
# insert code here
```

### Exercise 4.3

Remove this text, and add your answer for Exercise 7 here.


```r
# insert code here
```


```r
# insert code here
```

### Exercise 5.1

Remove this text, and add your answer for Exercise 8 here.


```r
# insert code here
```


### Excercise 3

Try this :D

ggplot(data = plastic_waste, 
       mapping = aes(x = continent, 
                     y = plastic_waste_per_cap)) +
  geom_violin()+
  geom_boxplot(width=.3, fill="green") +
  stat_summary(fun.y=median, geom="point") 
  
### Exercise 5.2 

Helpful reference:http://www.sthda.com/english/wiki/ggplot2-themes-and-background-colors-the-3-elements



