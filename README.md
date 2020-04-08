# droner
Coordinates remote command execution between servers and drones

This repo is great. It can even execute programs on a drone and pass the return value to the server, or engage in more complicated functionality as so in the droneServer program:

e.g.: if drone.getVelocity() > 0 then drone.move(0,1,0) end

Or, from the server itself, e.g.:

function dr(port, cmd)
  modem.broadcast(port, "return "..cmd)
  ayy = select(6, event.pull(1, "modem_message"))
  os.sleep(0.25)
  return ayy
end

while dr(port, "drone.getVelocity() > 0.1") do
  os.sleep(1)
end
