# GreenDataSet

This is the driving data collected by UIUC. Each trip under the `./trips` folder is named by its `timestamp`. The trip data consists of sensor data collected from in-vehicle smartphones and OBD interface. Drivers signed the agreement to release the data. 

## What is contained in this dataset?

Trips are collected in different times, some are a few years ago, some are more recent. Older trips may have some sensor readings missing. In general, under each trip folder, you can find the following.

1. accelerometer.txt
This is the Android's acceleration readings, in the format:
```
System_Time_Millisecond,x-axis,y-axis,z-axis
1509682461014,-0.83761597,8.308701,5.3856354
1509682461034,-1.0088501,8.407745,5.4886017
...
```

2. 