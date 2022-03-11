# CarND-Controls-PID
Self-Driving Car Engineer Nanodegree Program

## Proportional - Integral - Derivative (PID) Controller

The PID controller functions via correction of a signal through caluclation on some defined input error. In this case the resulting correction has a distinct term proportional to the error itself, one proportional to the integral of the error signal and one proportional to its derivative. The proportionality factors of this equation $K_p$, $K_i$ and $K_d$ (often referred to as gains) fully define our controller and have to be chosen according to the signal behavior that shall be controlled.

## Steering PID Controller for lanekeeping in a vehicle

In this case, the error signal is the distance towards the ideal path of the car on the road.
- The proportional factor $K_p$ is tries to steer the car towards the ideal path, but has a strong tendency to overshoot and due to the limits of the actual steering value (25 degrees) we can reach a chaotic behavior rather quickly where the car goes outside the road when only using proportional gain.
- The integral gain $K_i$ has the effect of eliminating a possible bias that exists in many real systems, and cannot be overcome by other types of gains.
- The differential gain $K_d$ is a nice way of counteracting the proportional overshoot and smoothes the approach of the actual system value towards the desired control value.

In this project, where we steer a car around a track in a simulator, the PID gais were chosen through trial-and-error by slowly turning on the proportional gain and trying to adjust the integral and derivative parts accordingly. It became obvious very quickly, that there is only a small bias present in the simulator and thus the integral gain was chosen to be very small! A minimization of the overall cross-track error was achieved by tuning P and D values.
