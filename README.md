# CS659

Install Arduipilot  
Install ROS ( Robot operating system)   
Install gazebo  
Install pre-trained YOLO model (darknet)  
  
run arduipilot   
run gazebo wolrd.xml   //  here we run the gazebo world to create environment e.g. hills  
run ./startsitl.sh  
run roslaunch iq_sim apm.launch  
run rosrun iq_gnc avoid   // to run  avoid.cpp code    
  
//  for 2 drones  
   
just change line 10 to => sim_vehicle.py -v ArduCopter -f gazebo-iris --console -It (t depend upon number of the drone) --out=tcpin:0.0.0.0:x(x is any available port)   


//

simulations are uploaded in github also in case given link in pdf doesn't work
