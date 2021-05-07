# Obstacle Avoidance in Quadcopter

Installing Ardupilot and MAVProxy  
Installing QGroundControl  
Installing Gazebo and ArduPilot Plugin  
Installing ROS and MAVROS  
Install gazebo  ( use `git clone https://github.com/osrf/gazebo_models.git` to get open source gaazebo models )
Install pre-trained YOLO/Darknet  
  
##  for 1 drone obstacle avoidance   
run commands in different terminals =>  

1) `roslaunch iq_sim onedrone.launch`  //  here we run the gazebo world to create environment  
2) `run ./startsitl.sh`  
    in the same terminal run other commands to control drone,  
    `mode guided`  
    `arm throttle`  
    `take off 15`    // 15 is height, you can change accordingly  
    `position x y z`  // to move drone from current position to some point with coordinates x, y, z
3) `run roslaunch iq_sim apm.launch`  
    
    We have to use the command `catkin build` to create avoid executable file from avoid.cpp file
4) `run rosrun iq_gnc avoid`   // to run avoid executable file which helps to avoid collision with obstacle.    
5) `rosrun iq_gnc sub ` // to run yolo
  
##  for 2 drones obstacle avoidance  

change command line 2 to ;  
`sim_vehicle.py -v ArduCopter -f gazebo-drone1 --console -It --out=tcpin:0.0.0.0:x` ( where x is avaiable port and t is drone number)  
e.g.  
for drone 1 : `sim_vehicle.py -v ArduCopter -f gazebo-drone1 --console -I0 --out=tcpin:0.0.0.0:8100 `  
for drone 2 : `sim_vehicle.py -v ArduCopter -f gazebo-drone2 --console -I1 --out=tcpin:0.0.0.0:8200 `


--------------------------------------------------------------------------------------------------------------------------------------------------------------------
simulations are uploaded in github also in case given link in pdf doesn't work
