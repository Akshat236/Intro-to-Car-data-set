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

Next we will graph the histogram for the distance of the car, it is evident that the majority of the cars have travelled a distance around 20km.

```{r}
hist(cars.data$dist, 20, col="red")
```

# Plotting a Box plot

We can now plot a Box plot, which will show the variation amongst our variables. We can deduce from the graph that the speed of the car has less variation compared to distance, meaning distance has a wider range of values. 

```{r}
boxplot(cars.data, main="Box Plot", xlab="Variable", ylab="Value", col = "red", pch=19)
```

# Plotting a Scatter plot

The scatter plot below suggests that there is a linear and positive correlation. Moreover, there is presence of systematic error, since the line of best fit does not pass through the origin. 

```{r}
plot(x=cars.data$speed, y=cars.data$dist, main = "Cars data Scatter plot", xlab="Speed", ylab="distance", pch=19, col="green")
lin.mod = lm(cars.data$dist~cars.data$speed)
pr.lm = predict(lin.mod)
lines(pr.lm~cars.data$speed, col="blue", lwd=0.7)
abline(mod <- lm(cars.data$dist ~cars.data$speed ))
coef(mod) #calculate slope
```
