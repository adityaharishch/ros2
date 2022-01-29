Documentation is at https://docs.ros.org

Apple silicon MacOS(Monterey) M1 build (271 packages are fully passing the build with this updated ros2.repos)

Build Instructions:

1. Install the necessary libraries and dependencies with brew from ROS2 Galactic MacOS Documentation(https://docs.ros.org)
2. mkdir ~/ros2_galactic
3. mkdir ~/ros2_galactic/src
4. cd ..
5. git clone https://github.com/dpbnasika/ros2/tree/galactic
5. vcs import src < ros2.repos
6. change the commit ID to "4c742d61d4f47a58492c1afbd825fad1c9e05a09" in Mimick_Vendor CMakeLists.txt (https://github.com/ros2/mimick_vendor/blob/galactic/CMakeLists.txt) in your local source packages.
7. arch -arm64 colcon build --symlink-install --packages-skip-by-dep python_qt_binding
8. . ~/ros2_galactic/install/setup.zsh

9. ros2 run demo_nodes_cpp talker in one terminal. 
10. ros2 run demo_nodes_py listener in another terminal.

you should see the helloworld example running.

Build Instructions video: https://www.youtube.com/watch?v=A7O1k2A_0iA
