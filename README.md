Pepper navgation ROS nodes
===========================

Bringing it up
--------------


```
roslaunch pepper_bringup pepper_full.launch
```


Teleop
------

```
$ roslaunch nao_teleop teleop_joy.launch
```

Mapping
-------

Using `gmapping`:

```
$ roslaunch pepper_nav_ros mapping.launch
```

To save the map, run:
```
$ rosrun map_server map_saver
```
**before** stopping ``gmapping``.


Navigation
----------



```
roslaunch pepper_nav_ros nav.launch map:=<full path to your map.yaml>
```
