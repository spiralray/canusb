# canusb
ROS node of LAWICEL CANUSB

##Install
clone this project into ~/catkin_ws/src

    cd ~/catkin_ws/src
    git clone https://github.com/spiralray/canusb.git
    cd ..
    catkin_make

##Usage

    rosparam set /canusb/baud 500k #Set 500Kbps
    rosparam set /canusb/port /dev/ttyUSB0 #Set CANUSB port
    rosrun canusb canusb.py

This node publish received messages on "/canrx". 

    rostopic echo /canrx

Message type is Int16MultiArray.

* First element of this array is StdId
* Second and the subsequent elements are data of received message

##Supported baudrate
* 10k
* 20k
* 50k
* 100k
* 125k
* 250k
* 500k
* 800k
* 1m

You can choose baudrate using rosparam.

    rosparam set /canusb/baud  500k

Test of transmitting

    rosrun canusb test.py

##Known issues
* Cannot manage extended format