# Reproducible Research: Peer Assessment 1


## Loading and preprocessing the data

Load the data:

```r
activity<-read.csv("activity.csv")
```



## What is mean total number of steps taken per day?


```r
## Histogram of the total number of steps taken each day
with (activity, hist(tapply(steps, date, sum), breaks=20, col="red", main="Histogram of the total number of steps taken each day", xlab="Number of steps"))
```

![](PA1_template_files/figure-html/histogram-1.png) 



## What is the average daily activity pattern?



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
