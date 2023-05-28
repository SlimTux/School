# GDP vs CO2 emissions
---
## Data

+ All the countries were randonly picked from a **[Datacenter](https://gigacalculator.com)**

  + **Countries** 
    + Bukina Farso
    + Cambodia
    + China 
    + Congo's Republic
    + Ghana
    + Iceland
    + Luxembourg
    + Moldova (ROMANIA)
    + Namibia
    + Panama
    + Russia
    + Rwanda
    + Samoa
    + Saint Kitts and Nevis
    + Seychelles
    + Solomon Islands
    + South Africa
    + Thailand 
    + The United Kingdom
    + Tunisia
---
### The data is from 2019
___
+ GDP
   +  GDP(per-capita)
   +  GDP(TOTAL)
+ CO2
  + CO2 (TOTAL)
___
### China 2019 🇨🇳🇲🇴🇭🇰 📹🕵️ (West Taiwan)
 + **CO2**
   + 8617 _MT-CO2_
+ GDP
  + 14.28$ Trillions
+ GDP ***per capita***
  + 10,409$
___
### ☦️🇷🇴Romania🇷🇴(Moldova🇷🇴is🇷🇴rightfully🇷🇴romanian.)☦️
+ **CO2**
  + 85 _MT-CO2_
+ GDP
  + 252$ Million
+ GDP  ***per capita***
  + 13,047$
---
### Russian Federation🐻🍺
+ **CO2**
  + 1622 _MT-CO2_
+ GDP
  + 1,693.11$ Billion 
+ GDP ***per capita***
  + 11.536$
---
### The Brits innit m8 (The United Kingdom)
+ **CO2**
  + 365 _MT-CO2_
+ GDP
  + 2,857.67$ Billion
+ GDP ***per capita***
  + 40,319$
---
### 🥶🏝️ (Iceland)
+ **CO2**
  + 3.6 _MT-CO2_
+ GDP
  + 2,857.67$ Billion
+ GDP ***per capita***
  + 40,319$
---
### Thailand🇹🇭
+ **CO2**
  + 290 _MT-CO2_
+ GDP
  + 2,857.67$ Billion
+ GDP ***per capita***
  + 40,319$
---
### Ghana🇬🇭
+ **CO2**
  + 9.7 _MT-CO2_
+ GDP
  + 70.04$ Billion
+ GDP ***per capita***
  + 2,177$
---
### South Africa🇿🇦
+ **CO2**
  + 467 _MT-CO2_
+ GDP
  + 338.53$ Billion
+ GDP ***per capita***
  + 6,689$
---
### Seychelles🇸🇨
+ **CO2**
  + 0.4 _MT-CO2_
+ GDP
  + $1.68$ Billion
+ GDP ***per capita***
  + 17,254$
---
### Samoa 🇼🇸(Tropical Taiwan)
+ **CO2**
  + 0.2 _MT-CO2_
+ GDP
  + 0.91$ Billion
+ GDP ***per capita***
  + 4,308$
---
### Cambodia🇰🇭
+ **CO2**
  + 5.1 _MT-CO2_
+ GDP
  + 25.87$ Billion
+ GDP ***per capita***
  + 1,671$
---
### Rwanda 💸☁️
+ **CO2**
  + 0.6 _MT-CO2_
+ GDP
  + 10.36$ Billion
+ GDP ***per capita***
  + 775$
---
### 🐟Solomon🐟Island🎣
+ **CO2**
  + 0.3 _MT-CO2_
+ GDP
  + 1.62$ Billion
+ GDP ***per capita***
  + 2,400$
---
### Luxembourg💰🔷🤑
+ **CO2**
  + 11 _MT-CO2_
+ GDP
  + 74$ Billion
+ GDP ***per capita***
  + 112,618$
---
### Namibia🇳🇦
+ **CO2**
  + 2.8 _MT-CO2_
+ GDP
  + 12,54$ Billion
+ GDP ***per capita***
  + 5,126$
---
### Burkina Farso🇧🇫(Fake Viet-nam)
+ **CO2**
  + 2 _MT-CO2_
+ GDP
  + 16.18$ Billion
+ GDP ***per capita***
  + 772$
---
### Congo line 🫥🇨🇬🫥
+ **CO2**
  + 2 _MT-CO2_
+ GDP
  + 12.75$ Billion
+ GDP ***per capita***
  + 2,289$
---
### Panama 🚢
+ **CO2**
  + 9,1 _MT-CO2_
+ GDP
  + 66.98$ Billion
+ GDP ***per capita***
  + 15,826$
---
### Tunisia🇹🇳(Fake Turkish flag)
+ **CO2**
  + 27 _MT-CO2_
+ GDP
  + 41.91$ Billion
+ GDP ***per capita***
  + 3,479$
---
### Meaw Island(Saint Kittens and Nevis)🐈
+ **CO2**
  + 0.2 _MT-CO2_
+ GDP
  + 1.11$ Billion
+ GDP ***per capita***
  + 23,219$
---
```{r} 
library(ggplot2)
data <- data.frame(
  group=c("CHINA ","RUSSIA ","South Africa ","UK ","Thailand ","Romania ","Tunisia ","Ghana ","Cambodia ","Panama ","LUX ","Congo ","BF ","Namibia ","Iceland ","Rwanda ","Seychelles ","Salmon Island ","Samoa ","Meow Island") , 
  value=c(10741,1692,467,365, 290, 77, 30, 19, 18, 13, 9.8, 7.3, 5.3, 4.1, 3.5, 1.8, 0.6, 0.3, 0.3, 0.3) , 
  number_of_obs=c(14.28,0.1693,0.014,0.005,0.0252,0.0041,0.0068,0.0025,0.0061,0.0074,0.0012,0.0016,0.0012,0.0025,0.0010,0.068,0.001,0.0091,0.001)
)
 
# Calculate the future positions on the x axis of each bar (left border, central position, right border)
data$right <- cumsum(data$number_of_obs) + 30*c(0:(nrow(data)-1))
data$left <- data$right - data$number_of_obs 
 
# Plot
ggplot(data, aes(ymin = 0)) + 
    geom_rect(aes(xmin = left, xmax = right, ymax = value, colour = group, fill = group)) +
    xlab("number of obs") + 
    ylab("value") 
```