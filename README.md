# droner
Coordinates remote command execution between servers and drones

This repo is great. It can even execute programs on a drone and pass the return value to the server, or engage in more complicated functionality as so in the droneServer program:

e.g.: if drone.getVelocity() > 0 then drone.move(0,1,0) end
