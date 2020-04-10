# Intro-to-Car-data-set
This repository provides a detailed description of how we can harness the Car data set to create, as well as analyze various types of plots.
# Introduction to Cars data set

This report will be guiding on how the cars data set can be used in R studio to graph and ananlyze graphs.

Format
A data frame with 50 observations on 2 variables.
[,1]	speed	numeric	Speed (mph)
[,2]	dist	numeric	Stopping distance (ft)

Disclaimer: the data set is recorded in the 1920s; Hence may be outdated and not reliable for use in 2020!!

```{r}
cars.data = cars
View (cars.data)
dim(cars.data)
```

Below we can find the array of integers(50) stored in the variables distance and speed. 
```{r}
str(cars.data)
```

# Plotting histograms
Histograms can be used to study the frequency of the variables(Speed and Distance)

First we will graph the histogram for the speed of the car, it is evident that the majority of the cars have a max speed of 18-20 km/hr. 

```{r}
hist(cars.data$speed, 20, col="Blue")
```
