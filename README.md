# Neurorobotics-Computational-Environment

## Webots + NAO Robot + ROS

(I will build a package that will put everything together later. Meanwhile, the following instructions allow you to operate NAO on Webots.)

1. Follow the installation steps of Webots in https://cyberbotics.com/doc/guide/installation-procedure.
2. Install webots_ros by using the command:

```
$ sudo apt-get install ros-melodic-webots-ros
```

3. Modify one of the launch files from webots_ros package:

```
$ cd /opt/ros/melodic/share/webots_ros/launch/
$ cp complete_test.launch complete_test.launch.bkup
$ vim complete_test.launch
```

4. In this launch file, replace the world directory with the one from NAO robot demo:

```
<arg name="world" value="/usr/local/webots/projects/robots/softbank/nao/worlds/nao_demo.wbt"/>
```

5. Download nao_demo_python.py from this repository and replace the original:

```
$ cd /usr/local/webots/projects/robots/softbank/nao/controllers/nao_demo_python/
$ cp nao_demo_python.py nao_demo_python.py.bkup
$ cp (nao_demo_python.py - the one from this repo) nao_demo_python.py
```

6. Launch the simulation:

```
$ roslaunch webots_ros complete_test.launch
```

7. On the left side of the simulator, you will see some details of the world file. Among those information, there will be also the robot description. Select NAO and, then, controller. Switch the controller to nao_demo_python.

8. Now, you have the robot running a simple generic code integrated with ROS. 


