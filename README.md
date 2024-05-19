# 4-Wheel-Differential-Drive-Robot-Using-Dockers

## Don't have ubuntu? 
## Don't worry. Docker got this all. 

### Run ROS2 package on your Windows/MAS-OS/Ubuntu without any installation of Ubunto or ROS or any other dependency.


Download dockers first from --> 
https://docs.docker.com/desktop/

Once docker is installed, pull the ros2 image file. For that open the terminal

```
docker pull aaids2024/ros2-desktop-vnc:foxy

```

Run the Docker image
```
docker run -it -p 6080:80 -v ~/development/ros-docker-tutorials --name foxy_vnc --security-opt seccomp=unconfined --shm-size=512m aaids2024/ros2-desktop-vnc:foxy

```
Output will look like this 
![](https://github.com/SaadRana17/4-Wheel-Differential-Drive-Robot-Using-Dockers/blob/main/t1.jpeg)


Now open browser and connect to localhost --> localhost:6080
Output will look like this 
![](https://github.com/SaadRana17/4-Wheel-Differential-Drive-Robot-Using-Dockers/blob/main/t2.jpeg)

## Congratulations!
### You are now running Ubuntu 20.04 with ROS2 foxy installed in it.

Now open the terminal in your browser ubuntu

Create ws_mobile directory
```
mkdir ws_mobile

```

Going in directory
```
cd ws_mobile/
```

Clone the package
```
git clone https://github.com/SaadRana17/4-Wheel-Differential-Drive-Robot.git

```

Going in package directory
```
cd 4-Wheel-Differential-Drive-Robot/

```

Source the environment
```
source /opt/ros/foxy/setup.bash

```
Installing missing dependency of cmake

```
sudo apt install cmake

```

Building workspace
```
colcon build
```

Sourcing the environment again
```
source /opt/ros/foxy/setup.bash
```

Sourcing the workspace
```
source ~/Desktop/ws_mobile/4-Wheel-Differential-Drive-Robot/install/setup.bash

```

Updating all dependences and packages
```
sudo apt update

```

Installing missing xacro dependences
```
sudo apt install ros-foxy-xacro

```

Run the launch file. This will open the 4-wheel-robot model in gazebo
```
ros2 launch mobile_robot gazebo_model.launch.py

```

![](https://github.com/SaadRana17/4-Wheel-Differential-Drive-Robot/blob/main/1_ws.gif)
![](https://github.com/SaadRana17/4-Wheel-Differential-Drive-Robot/blob/main/2_ws.gif)

Open new terminal and source the environment variable again
```
source /opt/ros/foxy/setup.bash

```

Start the teleop to operate robot from keyboard. Make sure teleop terminal window is open over on gazebo else robot won't move.
```
ros2 run teleop_twist_keyboard teleop_twist_keyboard

```

![](https://github.com/SaadRana17/4-Wheel-Differential-Drive-Robot/blob/main/3_ws.gif)
![](https://github.com/SaadRana17/4-Wheel-Differential-Drive-Robot/blob/main/4_ws.gif)


## If you want to learn more let's connect --> https://www.linkedin.com/in/rana-muhammad-saad/
