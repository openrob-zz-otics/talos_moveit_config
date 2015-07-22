To use this package you must also have the talos_simulator package installed.

Usage:

Bring up the simulator so that RViz can properly read the joint data of the robot:

    roslaunch talos_simulator talos.launch

Bring up the planning algorithms and controllers for moveit:

    roslaunch talos_moveit_config talos_moveit_planning_execution.launch sim:=true

Bring up the RViz Moveit Config which will allow you to move the arm around:

    roslaunch talos_moveit_config moveit_rviz.launch config:=true

That's all you need to know! All of the other launch files are helper scripts. Actually, more things about the development side/debugging side.

If you bring it up and see red in the RViz screen, select the status tab of the manipulation window and see what is in collision. Collisions need to be setup properly inside of the config/*.srdf file located in the talos_moveit_config package. Just look at the format existing there already and copy in some collision rules so the robot works, but make sure they're true otherwise the robot will try to plan through itself, or even the ground.
