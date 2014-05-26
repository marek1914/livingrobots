Living Robots
=============
 
Living Robots, is the Github repository for the new Ebook about LeJOS "Living Robots with EV3".

"Living Robots with EV3" is a ebook designed to learn about development of Robots with modern techniques and technologies. The book put the focus in the platform Lego Mindstorms EV3, Linux and the programming language Java.

If you enjoyed the previous ebook (http://juanantonio.info/lejos-ebook/) then book your copy now: http://juanantonio.info/about.htm

    05/04/2014: First commit
    05/25/2014: RPLIDAR Support for LeJOS

## Chapter 0:

Downloads: https://github.com/jabrena/livingrobots/raw/master/chapter0/docs/LRWE_Chapter0.pdf

## Chapter 1: Introduction

### Living Robots

#### Brity V2

Specifications:

    1x Lego Mindstorms EV3 Brick + EV3 Rechargable battery + USB Hub + Netgear WNA 1100
    1x Hitechnic Compass sensor
    1x EV3 IR Sensor
    1x Arduino One + Arduino Proto shield + Dexter breadboard adapter
    1x Robopeak RPLIDAR
    1x Smartphone + Chrome Web browser

![ScreenShot](https://raw.githubusercontent.com/jabrena/livingrobots/master/LDD/Base1/Base1_5.png)

## Chapter 2: Fundamentals of Robotics

Pending

## Chapter 3: Sensors

In this chapter, we will cover the most popular and useful sensors compatible with EV3 Brick.

### Exteroceptors sensors

Exteroceptors are sensors that measure the positional or force-type interaction of the robot with its environment. 

Sensors tested:

    Robopeak RPLIDAR
    EV3 IRSensor
    Hitechnic Compass Sensor
    Dexter GPS

#### RPLIDAR

RPLIDAR is a low cost 360 degree 2D laser scanner (LIDAR) solution developed by RoboPeak. The system can perform 360 degree scan within 6 meter range. The produced 2D point cloud data can be used in mapping, localization and object/environment modeling.

Data visualization with a Polar Chart.

    http://192.168.0.101/Radar/amcharts/polarChart.htm

![ScreenShot](https://github.com/jabrena/livingrobots/raw/master/chapter3/docs/RPLIDAR_livingRoom.png)

Note: It is necessary to launch the webserver:

    root@(none):~# httpd -v -h /home/lejos/www/

#### Sensor support

RPLIDAR Arduino Library: https://github.com/jabrena/livingrobots/raw/master/chapter3/arduino/RPLIDAR/Driver/RPLidarDriver_r1.0.zip

Arduino Sketch: https://github.com/jabrena/livingrobots/blob/master/chapter3/arduino/RPLIDAR/Sketches/simple_connect6/simple_connect6.ino

LeJOS Sensor Class: https://github.com/jabrena/livingrobots/blob/master/chapter3/ev3/RPLIDARTest/src/lejos/hardware/sensor/RPLIDARSensor.java

### Usage

Take a look a preliminar test using the Sensor.

https://www.youtube.com/watch?v=1XT2HOc5IsA

### Proprioceptors sensors

Proprioception in robotics means sensing the internal state of the robot or a part of it . For example the posture of a mechanical manipulator, leg or other jointed mechanism or the battery level.

Sensors tested:

    EV3 Battery

### Examples

    Example: IRSensor to detect a Beacon
    Example: The magic 8 ball using a EV3GyroSensor
    Example: How to integrate Arduino with EV3
    Example: How to use the sensor RPLIDAR
    Example: How to generate JSON data to view LIDAR data

## Chapter 4: Actuators

Pending

## Chapter 5: Navigation

In this chapter, user will learn basic concepts about Local & Global navigation

### Local navigation

#### Wheeled mobile robots

http://www.lejos.org/ev3/docs/lejos/robotics/navigation/DifferentialPilot.html

http://www.lejos.org/ev3/docs/lejos/robotics/localization/OdometryPoseProvider.html

http://www.lejos.org/ev3/docs/lejos/robotics/localization/CompassPoseProvider.html

####  Occupancy grid maps

A robot needs to know the environment to operate. A LIDAR sensor help to discover the environment.

In the following picture, you see a Polar View:

![ScreenShot](https://raw.githubusercontent.com/jabrena/livingrobots/master/chapter5/docs/OGM_PolarChart.png)

    http://192.168.0.101/Radar/amcharts/polarChart.htm

In the following picture you see the Occupancy grid map representation:

![ScreenShot](https://raw.githubusercontent.com/jabrena/livingrobots/master/chapter5/docs/OGM_WebView.png)

    http://192.168.0.101/ogm/index.htm

I have to analyze continue working in this development to create a map from the living room and evolve the system using Bayes theory.

http://www.cs.ox.ac.uk/people/michael.wooldridge/teaching/robotics/lect05.pdf

http://www.cs.cmu.edu/~motionplanning/lecture/Chap9-Bayesian-Mapping_howie.pdf

http://ais.informatik.uni-freiburg.de/teaching/ws12/mapping/pdf/slam02-bayes-filter-short.pdf

Once the robot has the environment to operate, it is possible to use some kind of Path Planning algorithm.

#### Local path planning

##### LeJOS development:

https://svn.code.sf.net/p/lejos/code/trunk/samples/src/org/lejos/sample/pathfinding/PathFinding.java

https://svn.code.sf.net/p/lejos/code/trunk/samples/src/org/lejos/sample/waypointnav/WaypointNav.java

##### Virtual Potential Fields

![ScreenShot](http://www.cs.mcgill.ca/~hsafad/robotics/report_files/image010.jpg)

http://www.cs.mcgill.ca/~hsafad/robotics/

## Chapter 6: Cognition

### Reactive Control

Pending

### Behavior-Based Control

Example: http://sourceforge.net/p/lejos/ev3/ci/master/tree/EV3BumperCar/src/EV3BumperCar.java

### Deliberative Control

#### FSM

The behaviours are modelled with a HFSM using Apache Commons SCXML.

Examples: https://github.com/jabrena/liverobots

### Examples

    Example: Simple bumper car

## Chapter 7: Computer vision

Pending

## Chapter 8: Web interfaces

In this Chapter, the reader will learn many stuff about Web Servers and  Web interfaces for robots with EV3 Brick.

### Web Servers

In this section, user will learn the different among httpd and other developments in Java to run a Web Server as NanoWeb server.

    root@(none):~# start-stop-daemon -K -n httpd
    stopped httpd (pid 1823)
    root@(none):~# httpd -v -h /home/lejos/www/

An example when the httpd is pretty busy:

    Mem: 49048K used, 11812K free, 0K shrd, 516K buff, 25556K cached
    CPU:   8% usr  35% sys   0% nic   0% idle   0% io  15% irq  39% sirq
    Load average: 11.89 12.35 10.50 17/101 9146
      PID  PPID USER     STAT   VSZ %MEM %CPU COMMAND
     1551  1197 root     S     178m 300%  16% /home/root/lejos/ejre1.7.0_55/bin/java
     1735     1 root     R     2880   5%  11% httpd -v -h /home/lejos/www/ 

### Web Interfaces

In this section, user will learn basic stuff about Modern web development.

![ScreenShot](https://raw.githubusercontent.com/jabrena/livingrobots/master/chapter8/docs/remoteControl.jpg)

### Examples

    Example: Web remote control with Websockets
    Example: Data visualization for RPLIDAR
    Example: Occupancy grid map viewer

## Chapter 9: Communications

This chapter covers the following technologies: Websockets, Http, RMI, D-Bus & I2C.

## Chapter 15: Hacking robots

It is very important to ensure that your robot operates in a secure environment. Learn some stuff about security for Robots and avoid future robot's hacks.

![ScreenShot](https://raw.githubusercontent.com/jabrena/livingrobots/master/chapter15/docs/Tachikoma.png)

In this chapter you will learn some concepts about security for Unix. Remember that your EV3 Brick run over a Busybox distro.

Nano Web server running on EV3 and suffering a DOS Attack:

    Mem: 59800K used, 1060K free, 0K shrd, 48K buff, 4288K cached
    CPU:  23% usr  26% sys   0% nic   0% idle  23% io   9% irq  17% sirq
    Load average: 3.60 1.78 0.77 1/373 2030
    PID  PPID USER     STAT   VSZ %MEM %CPU COMMAND
    1577  1538 root     S     266m 447%  43% /home/root/lejos/ejre1.7.0_55/bin/java -classpath /ho
        4     2 root     SW       0   0%  11% [events/0]
      430     2 root     DW       0   0%   8% [mmcqd]
     1538  1184 root     S     179m 301%   5% /home/root/lejos/ejre1.7.0_55/bin/java -classpath /ho
      180     2 root     DW       0   0%   4% [kswapd0]
     1594  1567 root     R     3072   5%   2% top 

### Examples

The examples included in this chapter are:

    Example: Discover ports opened in your EV3 Brick
    Example: Hack your SSH root account using Brute force
    Example: Read /var/volatile/log/ to discover ssh attacks
    Example: A mini example about a DOS Attack to the service httpd included Busybox
    Example: Shell scripts to remove some no necessary processes
    Example: Scheduling a task with Cron4J
    Example: NTP Client (Using classes from project EV3Menu)

### Exercises

    Exercise 1: How to add a program in the startup
    Exercise 2: Create a Virus for EV3 brick

## Annexes

## Annex 1: Getting started with LeJOS

### References

http://sourceforge.net/p/lejos/wiki/Getting%20started%20with%20leJOS%20EV3/

## Annex 2: Busybox

LeJOS project uses Busybox as the way to offer a Linux experience. It was specifically created for embedded operating systems with very limited resources. BusyBox provides several stripped-down Unix tools in a single executable file. The authors dubbed it "The Swiss Army Knife of Embedded Linux", as the single executable replaces basic functions of more than 300 common commands

In this Annex, the reader will learn how to use Busybox in a EV3 environment.

Download preview: https://github.com/jabrena/livingrobots/raw/master/annex2/docs/LRWE_Annex2_Busybox_Preview.pdf
Exercises: https://github.com/jabrena/livingrobots/raw/master/annex2/docs/LRWE_Annex2_Busybox_Exercises.pdf


