Pepper Navigation ROS nodes
===========================

Bringing it up

roslaunch pepper_bringup pepper_full.launch
```

![Some of Pepper's TF frames](doc/frames.png)

Teleop
------

Required packages:
- ``ros-<version>-joy``
- ``nao_teleop``: [http://wiki.ros.org/nao_teleop](http://wiki.ros.org/nao_teleop)

Then:
```
$ roslaunch nao_teleop teleop_joy.launch
```

Note: to enable the joystick control, press button **10** on the joystick, not
9.

Mapping
-------

![Mapping with gmapping](doc/mapping_pepper.png)

Using `gmapping`:

```
$ roslaunch pepper_nav_ros mapping.launch
```

Localisation
------------

![Localisation with AMCL](doc/localisation_pepper.png)

First, the map server:

```
$ rosrun map_server map_server <path to map>/map.yaml
```

Then, AMCL:
```
$ rosrun amcl amcl scan:=/pepper_robot/laser
```

To save the map, run:
```
$ rosrun map_server map_saver
```
**before** stopping ``gmapping``.


Navigation
----------


![Path planning](doc/motion_planning_pepper_rviz.png)

Both localisation (using `AMCL`) and planning are provided from:

```
roslaunch pepper_nav_ros nav.launch
```

A custom map can be provided:

```
roslaunch pepper_nav_ros nav.launch map:=<full path to your map.yaml>
```

