# Pioneer3DX-NAV
Creator: Riddhiman Raut
Jadavpur University


First attempt at creating a working navigation stack on a pioneer 3dx robot. Developers are welcome to improve upon it.

1)Run RosAria on the robot pc. 

2)On the piggyback laptop, roslaunch freenect_launch freenect.launch depth_registration:=true. For my kinect, of course

3)rosrun depthimage_to_laserscan depthimage_to_laserscan image:=/camera/depth_registered/image_raw. For fake laser data

4)roslaunch rtabmap_ros rtabmap.launch rtabmap_args:="--delete-dbs-on-start" rviz:=true rtabviz:=false, gives me map->odom transform.

5) Run teleop in the remote pc. generate a 2-d map in rtabmap, save it on map_server

6)Roslaunch p3dx_navigation move_base_rosaria.launch. open rviz, 2d point estimate works well. Not perfect, but not too bad either.

7)Set a goal using 2d Nav goal.

