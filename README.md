# GreenDataSet

This is the driving data collected by UIUC. Each trip under the `./trips` folder is named by its `timestamp`. If there are multiple segments of the same trip, its filename may end with a letter as well. The trip data consists of sensor data collected from in-vehicle smartphones and OBD interface. This is not human subject research (it is research on performance of vehicle-related systems, not humans), and no personal information is in this release.

We currently released around 2400 trips, all compressed in `.tar.gz` format. If you have any questions, please send to zhao97@illinois.edu.



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
Older trips (the first ones you see under the trips folder) may not have this file, due to missing sensor readings.

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

This is the vehicle's ID, type, and the trip date time. For privacy issues, the vehicle specific make, model, and year are not given. 
```
VID, Type, Date
T1,Mid-size Sedan,2012-03-14,14:15:53
```

7. map.html

This is the vehicle's trip in Google Maps html format, you can view the trip in browser. The red dots are 1Hz trace, the color represents fuel rate (the darker the more fuel in the last second). The blue line is the result of map matching using ORSM API. 



## This data is released free of charge. However, to use the data in a publication, please cite any of the following papers:
```
@inproceedings{zhao2019greenroute,
  title={GreenRoute: A Generalizable Fuel-Saving Vehicular Navigation Service},
  author={Zhao, Yiran and Yao, Shuochao and Liu, Dongxin and Shao, Huajie and Liu, Shengzhong and Abdelzaher, Tarek},
  booktitle={2019 IEEE International Conference on Autonomic Computing (ICAC)},
  year={2019},
  organization={IEEE}
}
@inproceedings{zhao2017greendrive,
  title={Greendrive: A smartphone-based intelligent speed adaptation system with real-time traffic signal prediction},
  author={Zhao, Yiran and Li, Shen and Hu, Shaohan and Su, Lu and Yao, Shuochao and Shao, Huajie and Wang, Hongwei and Abdelzaher, Tarek},
  booktitle={Cyber-Physical Systems (ICCPS), 2017 ACM/IEEE 8th International Conference on},
  pages={229--238},
  year={2017},
  organization={IEEE}
}
```


## Data Usage

We encourage people to use this dataset for research purposes related to cyber-physical systems, machine learning, Internet-of-Things, etc. For example, we are using this dataset to build a fuel-saving vehicle routing system which can be deployed potentially in any city. You can use the data to train fuel consumption models based on features from OSM data and OSRM API. You can utilize multi-modal sensor data to train models that detect bad driving behaviors, or help calculate vehicle position in cases where GPS signal is not available in tunnels or Manhattanized areas. You can dive deep into the data and find interesting correlations between the different sensor sources, or you can find correlated phenomena around some points of interest, or around certain time of day. We would love to see smart city related systems come to live!

## Additional Information

There is a website describing how we collected the data recently. See http://greengps.cs.illinois.edu/green/index


## A partial overview

![alt text](https://github.com/zyrgit/mystuff/blob/master/GreenDrive/Traces.png)


