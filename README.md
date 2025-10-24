# Recording a bag file

Once your ROS 2 environment and the repositories for running Robile in simulation are ready, record a bag file to capture the topics you need. Start the Robile simulation (see the simulation tutorial). If any packages are reported missing, install them with pip and report the issue on the LEA forum so the docs can be updated.

Refer to the ROS 2 documentation for details on bag files and how to record/play them. If ros2bag is not installed, add it with:

```bash
sudo apt-get install ros-humble-ros2bag
sudo apt-get install ros-humble-rosbag2-storage-default-plugins
```

With the simulator running, open a new terminal, source your ROS 2 Humble workspace, change to the directory where you want the bag saved, and record all topics:

```bash
ros2 bag record -o file_name -a
```

Operate the robot in the simulator while recording. Press Ctrl+C to stop; this creates a directory named file_name containing a .db3 and a .yaml file. To record only specific topics, replace `-a` with the desired topic names separated by spaces. For this assignment, the relevant topics are `/scan`, `/tf`, and `/tf_static`, so use:

```bash
ros2 bag record -o file_name /scan /tf /tf_static
```

Before visualising or transforming the data, install the required Python packages:

```bash
pip install rosbag2_py
pip install rosbags
pip install transforms3d
```

Then import the necessary Python modules to work with the bag file and its contents.

# important resources : https://ternaris.gitlab.io/rosbags/topics/rosbag2.html
#                        https://docs.ros.org/en/humble/Installation/Alternatives/Ubuntu-Development-Setup.html