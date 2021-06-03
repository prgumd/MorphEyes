# MorphEyes
MorphEyes: Variable Baseline Stereo For Quadrotor Navigation


**MorphEyes** by <a href="http://prg.cs.umd.edu"><i>Perception & Robotics Group</i></a> at the Department of Computer Science, <a href="https://umd.edu/">University of Maryland- College Park</a>.

![MorphEyes: Variable Baseline Stereo For Quadrotor Navigation](http://prg.cs.umd.edu/research/MorphEyes_files/Banner.png)
(a) Flying through a forest, (b) flying through a dynamic gap, (c) detecting an independently moving object, and (d) our quadrotor with different baselines from 100 mm to 300 mm.

### Abstract

Morphable design and depth-based visual control are two upcoming trends leading to advancements in the field of quadrotor autonomy. Stereo-cameras have struck the perfect balance of weight and accuracy of depth estimation but suffer from the problem of depth range being limited and dictated by the baseline chosen at design time. In this paper, we present a framework for quadrotor navigation based on a stereo camera system whose baseline can be adapted on-the-fly. We present a method to calibrate the system at a small number of discrete baselines and interpolate the parameters for the entire baseline range. We present an extensive theoretical analysis of calibration and synchronization errors. We show casethree different applications of such a system for quadrotor navigation: (a) flying through a forest, (b) flying through an unknown shaped/location static/dynamic gap, and (c) accurate 3D pose detection of an independently moving object. We show that our variable baseline system is more accurate and robust in all three scenarios. To our knowledge, this is the first work that applies the concept of morphable design to achieve a variable baseline stereo vision system on a quadrotor.

- [Project Page](https://prg.cs.umd.edu/MorphEyes)
- [Paper](https://prg.cs.umd.edu/research/MorphEyes_files/MorphEyes.pdf)
- [arXiv Preprint](https://arxiv.org/abs/2011.03077)


### Supplementary Hardware Tutorial

1. Setting up the quadrotor to hover using on-board computation and sensing 

The first step involves building a quadrotor called PRGCorgi210$$\alpha$$ which is a 210mm sized quadrotor based on Ardupilot. Please refer to the step by step instructions [here](https://github.com/prgumd/PRGFlyt/wiki/PRGCorgi). 

2. Setting up the StereoPiv1

The second step is to setup StereoPiv1 with OpenCV, ROS and MAVROS to control the quadrotor. Start by installing the Raspbian buster image with openCV from [here](https://drive.google.com/file/d/1xlkvZMl9gJGm4Gy1oVlGknHywDnvy5gS/view?usp=sharing). More instructions can be found [here](https://wiki.stereopi.com/index.php?title=Main_Page). Then compile and install ROS from source following instructions [here](http://wiki.ros.org/ROSberryPi/Installing%20ROS%20Melodic%20on%20the%20Raspberry%20Pi). Finally install MAVROS along with its dependency packages from [here](https://github.com/mavlink/mavros).

3. Actuonix Servo Control

The third step is to setup the [Actuonix Servo](https://www.actuonix.com/L12-R-Linear-Servo-For-Radio-Control-p/l12-r.htm) with StereoPi. In order to control the motor, attach the signal wire to PWM output pin of an Arduino or Teensy. Control the servo by sending the PWM signal (using the standard [<Servo.h>](https://www.arduino.cc/reference/en/libraries/servo/write/) arduino library) from the microcontroller which takes serial input from StereoPi. Use [Pyserial](https://pyserial.readthedocs.io/en/latest/shortintro.html) to send command from the StereoPi to the microcontroller. You should now be able to control the servo motors via StereoPi in python.


## License:
Copyright (c) 2021 Perception and Robotics Group (PRG)
