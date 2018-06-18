# Intersection PLC
  
An intersection manager that is designed to be run in TwinCAT 3 XAE.  
  
## Code Setup
The overall managing code is contained in the *MAIN (PRG)* file. This begins by checking the different counting values and deciding what to do based on those values. *MAIN* then calls the *randomSensors()* function which randomly queues cars as a way of testing the system. Then *counterMaintenance()* which works as checking and updating the counters (just so that it is all in one place and not spread throughout the code). Then each of the individual lights are called and the logic for those lights are contained in there.  
  
*Glbl* is the global varaible list that is accessed throughout the code. This containes the active (green or yellow) for each light, the counters for each state (comments describe which state corresponds to which lights), the sensors for each lane that say "a car is here", and a sensor count for each lane that says "x # of cars are here".  
  
The Helper Functions folder contains three programs. *counterMaintenance()* run through the different states and checks the sensors and a maintenance routine to make sure that the counters are in the right place. *maximum()* returns the maximum value of all of the  counters to make check against the active counters to choose the correct state to turn on. *randomSensors()* chooses a random sensor to activate once every 5 seconds (on average).  
  
The *01_NorthLight*, *02_SouthLight*, *03_EastLight*, and *04_WestLight* all contain very similar code, slightly changed for the individual lights. 
