# GreenDataSet

This is the driving data collected by UIUC. Each trip under the `./trips` folder is named by its `timestamp`. The trip data consists of sensor data collected from in-vehicle smartphones and OBD interface. Drivers signed the agreement to release the data. 

## What is contained in this dataset?

Trips are collected in different times, some are a few years ago, some are more recent. Older trips may have some sensor readings missing. In general, under each trip folder, you can find the following:

1. accelerometer.txt

This is the Android's acceleration readings:
```
System_Time_Millisecond,x-axis,y-axis,z-axis
1509682461014,-0.83761597,8.308701,5.3856354
1509682461034,-1.0088501,8.407745,5.4886017
...
```

2. magnetometer.txt

This is the Android's magnetometer readings:
```
System_Time_Millisecond,x-axis,y-axis,z-axis
1509682461015,-10.409546,-7.470703,-3.6346436
1509682461035,-10.435486,-6.60553,-3.3355713
...
```
Older trips may not have this file, due to missing sensor readings.

3. gyroscope.txt

This is the Android's gyroscope readings:
```
System_Time_Millisecond,x-axis,y-axis,z-axis
1509682461015,0.007507324,0.0043029785,-0.0077209473
1509682461035,0.010299683,0.010681152,-0.011962891
...
```

4. linear_acceleration.txt

This is the Android's linear acceleration readings, which is acceleration excluding gravity component:
```
System_Time_Millisecond,x-axis,y-axis,z-axis
1509682461018,1.2512953,-0.065561295,0.538465
1509682461041,0.51145506,0.15923977,0.7462945
...
```

5. gps_fuel.txt

This is the OBD interface readings, combined with GPS readings, rendered at 1Hz. 
```
GPS_Time_Millisecond,System_Time_Millisecond,GPS_Latitude,GPS_Longitude,GPS_Speed,GPS_Altitude,GPS_Bearing,GPS_Accuracy,Fuel_Consumption,OBD_Engine_RPM,OBD_Speed,OBD_Throttle_Position
1509682464000,1509682462748,40.101429,-88.234914,9.75,189.0,89.2,3.0,0.436,1573.3,34.7,15.42
1509682465000,1509682463749,40.101431,-88.234798,9.50,189.0,88.9,3.0,0.391,1509.3,33.3,14.12
...
```
The `GPS_Time_Millisecond` is given by the GPS samples, which is different from the Android's system time `System_Time_Millisecond`. `GPS_Speed` is in `m/s`, `GPS_Altitude,GPS_Accuracy` is in meters, `GPS_Bearing` is between `0-360` degree, `Fuel_Consumption` is the total fuel (in grams) consumed in this second. `OBD_Speed` is in `km/s`.


6. info.txt

This is the vehicle's ID plus the trip date time. For privacy issues, the vehicle specific make, model, and year are not given. 
```
VID Date
V2 2017-11-02,23:14:22
```

7. map.html

This is the vehicle's trip in Google Maps html format, you can view the trip in browser. The red dots are 1Hz trace, the color represents fuel rate (the darker the more fuel in the last second).


## A partial overview

![alt text](https://github.com/zyrgit/mystuff/blob/master/GreenDrive/Traces.png)


