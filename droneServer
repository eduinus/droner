local component = require("component")
local event = require("event")
local modem = component.modem

port = 2413 -- change me to an available port that a drone is listening to.

modem.open(port)
modem.broadcast(port, "drone=component.proxy(component.list('drone')())")
while true do
  local cmd=io.read()
  if not cmd then return end
  modem.broadcast(port, cmd)
  print(select(6, event.pull(5, "modem_message")))
end
