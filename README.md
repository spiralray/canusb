# canusb
ROS node of LAWICEL CANUSB

##Install
clone this project into ~/catkin_ws/src

    cd ~/catkin_ws/src
    git clone https://github.com/spiralray/canusb.git
    cd ..
    catkin_make

##Usage

    rosparam set /canusb/port /dev/ttyUSB0 #Set CANUSB port
    rosrun canusb canusb.py

This node publish received messages on "/canrx". 

    rostopic echo /canrx

Message type is Int16MultiArray.

* First element of this array is StdId
* Second and the subsequent elements are data of received message

Test of transmitting

    rosrun canusb test.py

##Known issues
* Only supports 500kbps baud.
* Cannot manage extended format