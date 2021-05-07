# Obstacle Avoidance in Quadcopter

Install Ardupilot and MAVProxy  
Install QGroundControl  
Install Gazebo and ArduPilot Plugin  
Install ROS and MAVROS  
Install gazebo  ( use `git clone https://github.com/osrf/gazebo_models.git` to get open source gaazebo models )  
Install pre-trained YOLO/Darknet (in file `ros.yaml`  change the image topic from `/camera/rgb/image_raw` to `/webcam/image_raw`)
  
##  For 1 drone obstacle avoidance   
run commands in different terminals =>  

1) `roslaunch iq_sim onedrone.launch`  //  here we run the gazebo world to create environment  
2) `./startsitl.sh`  
    in the same terminal run other commands to control drone,  
    `mode guided`  
    `arm throttle`  
    `take off 15`    // 15 is height, you can change accordingly  
    `position x y z`  // to move drone from current position to some point with coordinates x, y, z
3) `roslaunch iq_sim apm.launch`  
    
    We have to use the command `catkin build` to create avoid executable file from avoidance_sol.cpp file
4) `rosrun iq_gnc avoidance_sol`   // to run avoid executable file which helps to avoid collision with obstacle.    
5) `rosrun iq_gnc sub ` // to run yolo
  
##  For 2 drones obstacle avoidance  

change command line 2 to ;  
`sim_vehicle.py -v ArduCopter -f gazebo-drone1 --console -It --out=tcpin:0.0.0.0:x` ( where x is avaiable port and t is drone number)  
e.g.  
for drone 1 : `sim_vehicle.py -v ArduCopter -f gazebo-drone1 --console -I0 --out=tcpin:0.0.0.0:8100 `  
for drone 2 : `sim_vehicle.py -v ArduCopter -f gazebo-drone2 --console -I1 --out=tcpin:0.0.0.0:8200 `


--------------------------------------------------------------------------------------------------------------------------------------------------------------------
simulations are uploaded in github also in case given link in pdf doesn't work
