# Reproducible Research: Peer Assessment 1


## Loading and preprocessing the data

Load the data:

```r
activity <- read.csv("activity.csv")
```



## What is mean total number of steps taken per day?


```r
## calculate total number of steps each day for use in the histogram and the calculations of mean and median after
totalSteps <- with (activity, tapply(steps, date, sum))

## Histogram of the total number of steps taken each day
hist(totalSteps, breaks=20, col="red", main="Histogram of the total number of steps taken each day", xlab="Number of steps")
```

![](PA1_template_files/figure-html/histogram-1.png) 


```r
meanTotalSteps <- round(mean(totalSteps[!is.na(totalSteps)]), 2)
medianTotalSteps <- median(totalSteps[!is.na(totalSteps)])
```

Mean total number of steps taken per day:       1.076619\times 10^{4}  
Median total number of steps taken per day:     10765



## What is the average daily activity pattern?

```r
meanIntervalSteps<-with (activity, tapply(steps[!is.na(steps)], interval[!is.na(steps)], mean))
intervals<-unique(activity$interval)
plot(intervals,meanIntervalSteps, type="l", main="Time series plot of average steps for each 5 minute interval", xlab="Time intervals", ylab="Average number of steps")
```

![](PA1_template_files/figure-html/time-1.png) 


```r
maxInterval <- intervals[match(max(meanIntervalSteps),meanIntervalSteps)]
```

On average across all the days in the dataset, the maximum number of steps is in interval:      835


## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
