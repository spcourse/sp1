# Assignment: Sensor data 

A mobile phone contains many delicate sensors that collect information about the position, speed and acceleration of the device. We have collected these inputs during a car ride and stored the data in a file with a frequency of 1[Hz]. We started collecting the data when the car was located on the A4 highway where it joins the A10 highway. We stopped collecting data when the car arrived at the Nikhef. 

![Map of the route](../../assets/KaartAmsterdamKlein.png)

The sensor data is available in the file `AutoRitData.csv` and can be downloaded via the following link:

[../../data/AutoRitData.csv](AutoRitData.csv)

At the top of the file is a short short description about the information contained in each field. This is typically how a data file is formatted: easy to read automatically, but sometimes it lacks clear descriptions of what each field precisely is. It should still be manageable to deduct how to use each field. So first try to figure out which data is contained in what field and how each part of it is represented, before discussing with your fellow students about the data file. It's (a) good practice!

Write a program **car_ride.py** that traverses the data file, processes said data and answers the following questions.

## Traveled distance

Create a graph of the speed of the car (km/h) as a function of the time and use the data to estimate the traveled distance in total.

Create a graph of the position of the car and color the route green (red) where the speed of the car was more (less) than 50 km/hour.

## Testing

Now you're ready to test with checkpy:

    checkpy car_ride
