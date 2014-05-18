# Reproducible Research: Peer Assessment 1


## Loading and preprocessing the data

Set here the working directory and then load the data.


```r
setwd("C:/Users/Selim/Documents/GitHub/RepData_PeerAssessment1")
data <- read.csv("activity/activity.csv")
```


No transformation of the data is necessary.

## What is mean total number of steps taken per day?

Store in a new variable the data without the NA values.


```r
data2 <- data[!is.na(data$steps), ]
totalStepsPerDay <- aggregate(data2$steps ~ data2$date, data = data2, FUN = sum)
```



```r
hist(totalStepsPerDay[, 2], breaks = seq(from = -1, to = 25000, by = 2000))
```

![plot of chunk unnamed-chunk-1](figure/unnamed-chunk-1.png) 



```r
meanTotalSteps <- mean(totalStepsPerDay[, 2])
medianTotalSteps <- median(totalStepsPerDay[, 2])
meanTotalSteps
```

```
## [1] 10766
```

```r
medianTotalSteps
```

```
## [1] 10765
```



## What is the average daily activity pattern?



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
