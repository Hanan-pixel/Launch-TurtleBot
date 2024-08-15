# Launch-TurtleBot

Install TurtleBot Package:

First, ensure that your system is up to date:
```ruby
sudo apt-get update
sudo apt-get upgrade
```
<img width="786" alt="Screenshot 2024-08-15 at 11 29 04 AM" src="https://github.com/user-attachments/assets/6a489ecd-6308-4bad-86ff-d0932052751f">


## Noetic (for Ubuntu 20.04):

Install the TurtleBot and TurtleBot Simulation Packages:
```ruby
sudo apt-get install ros-noetic-turtlebot3
sudo apt-get install ros-noetic-turtlebot3-simulations

```
## Create a Map and Launch Navigation:

First, launch the TurtleBot in a simulation environment:
```ruby
roslaunch turtlebot3_gazebo turtlebot3_world.launch
```
<img width="1345" alt="Screenshot 2024-08-15 at 11 45 29 AM" src="https://github.com/user-attachments/assets/496fcd2d-e936-4d6b-b053-ebe06ab5242a">

- To create a map, use the SLAM (Simultaneous Localization and Mapping) feature:
```ruby
roslaunch turtlebot3_slam turtlebot3_slam.launch

```

<img width="1345" alt="Screenshot 2024-08-15 at 12 03 58 PM" src="https://github.com/user-attachments/assets/404d221b-53e4-43ba-a3b0-3ac3bb7405a7">

- Once the map is created, save it:
```ruby
rosrun map_server map_saver -f ~/map
```
- Launch navigation using the saved map:
```ruby
roslaunch turtlebot3_navigation turtlebot3_navigation.launch map_file:=~/map.yaml
```
