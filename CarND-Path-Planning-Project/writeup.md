The simulator delivers a number of parameters like location of car, velocity, yaw rate, speed, frenet coordinates and sensor fusion data. 

We executed this project using a spline function that fits a line to merge the points in a fairly smooth function. We decided to use spline as it a library that is made well and can reduce computations. After line fitting, we feed the points back along with that line to the simulator.

## Prediction

The data taken form the sensor fusion and is used in the simulator to generate the exact prediction of outcome of the project. With the help of sensor fusion data we can derive the data about the other cars that are nearby and then can  predict the behaviour of them. Thus we can change the behaviour of our simulated car on the basis of the prediction of other car's behaviour.

## Behaviour Planning

The developed algorithm for behaviour planning is as given below-:

The car on initiation checks about 30 m ahead if there are any car present ahead of it.
If the car senses anything about  30 m a ahead, it starts to slow down little bit such that it can change the lane.
It the car tries to check for the left lane first, if finds it free as it contains no vehicle ahead of 30 m  and 10 m behind. The concept of checking behind because when we are changing lanes there is chance of collision happening with the cars that are moving point to point parallel.
If left lane is not available then it moves forward by checking  the right lane whether to switch  and check if it is free and contains no vehicle ahead of 30 m and 10 m behind .
If there are no further  option for lane change, then it stays in the current lane without colliding with the car ahead.

## Trajectory Generation

The car calucates the trajectory based on its own calculated speed, the speed of surrounding cars, current lane, intended lane and past points. 

To make trajectory further more smoother, we used more points. 

If there are no previous points then we calculate the previous points from the current yaw and current car coordinates. 

Also the 3 points are added in next 30, 60, 90 meters to trajectory. All these points are shifted to car reference angle.
