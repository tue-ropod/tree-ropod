# tree-devpc
Repository containing the rosinstall file with the structure of the whole software. This one particularly for the ropod.

For installation run the install_software script.
```
./install_software
```

Keep in mind that the robot should have access to all the repositories, meaning that probably you need to add a ssh_key to the repositories server.

Though is indicated as a dependency, you might need to manually install the costmap-converter module:

```
sudo apt-get install ros-kinetic-costmap-converter
```

The branch of `ropod-common` should be changed to `develop` branch if `catkin build` fails.

Once the software is compiled at the robot, give access of raw ethercat data to the low-level-control executable. For instance:

```
sudo setcap 'CAP_NET_RAW+ep CAP_SYS_NICE+eip' /home/ropod/ropod-project-software/catkin_workspace/devel/lib/ropod_4wheel_tdistkinb_cntr/ropod_4wheel_tdistkinb_cntr_node 
```
