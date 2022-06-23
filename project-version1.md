
# Project Version 1.

## Architecture

### Description

![arch](arch.png?raw=true "Arch")


This is a semi-autonomous car world multi-player game engine.

* CARS
  * They drive on a grid and are usually controlled by user (version 2 is semi-autonomous braking)
  * They can only drive in one of 4 directions (up, down, left, right)
  * They have a velocity

* MOOSE 
  * They stand still and sometimes move, but slowly. They try to block cars.

* POT-HOLES
  * They are in fixed locations. (but could move)

A car drives on the grid. There can be up to 5 cars. 
Moose are pre-allocated and sims (or someone can drive them?)

Cars wrap around at same velocity if they go off the side of the grid.

Collision 
 * If a Car hits a Moose it is stuck for 2.5 seconds * Speed factor
 * If a Car hits a Wall it is stuck for 5 seconds * Speed factor
 * If a Car hits another their cumulative speed determines wait 

### Implementation

Team 1: Driver and Map View (LiveView)

Team 2: Simulation (Process Control)

Team 3: Map and World (Management)


Driver sends message to backend and backend routes to Car.

Car-creator module (Supervisor?)
Car accepts speed or direction changes and changes state. Can do this as often as message are received.
Car receives initial position from world
Car receives "tick" message which is when it computes it's new position based on speed.
-- Maximum speed is one grid position per tick

Moose-process (module)

World sets up blank map
World creates Moose
World creates Walls (these are one grid space each) -> Active grid.

World send Go message to all processes.
Process all send messages to their subscribed drivers.

World loop
 * Tick is sent to every process
 * Process (Cars, Moose, Pot-holes) update their position
 * World then collects new position
 * World updates the map
 * Map is published to all subscribers

 Discussion
 * How do we know cars have updated - what if they don't move in time?
 * How do we establish the maximum speed
   * 1 tick = 1 grid
   * .5 grid
   * .2 grid
 * Drivers have time to change course before the tick
 * But when the simulation runs fast there could be 50 ticks a second

 When world gets all positions, it then creates the Map.
 If there a Car is in same grid position as a Moose or Pot Hole then it is stuck.
 Car will be notified of time penalty and must obey. Cheating not allowed.

## Driver

### User interface

A Phoenix Live View application with two views:
 * Driver
 * Map and Game control


The Driving View must be separate from the Map View (separate pages)

Input: Name
Button: Register
Display: Speed or "Stuck"
Display: "Obstacle" -- Version 2 -- 
Button: Turn Right
Button: Turn Left
Button: Accelerate
Button: Brake

The Map view must be able to see some indication (1..5 or something?)

Maps can be pre-seeded with Pot-holes and Moose somehow.

Button to press Go. 

Two main live views:


Send the map to the server.
Map is sent back every change. display it.

### Functionality

Users input their name and press register. This sends a registration message to the server.

Once registered, they wait for a "GO" message from the server. 

Pressing buttons sends messages to the server.


## Simulation

A car is like the CPU of the car. In the first version it just takes commands from it's driver.
In future it might take actions.

Supervisor (car, pot-hole, moose)
Cars hold state (position, speed, direction)
Cars calculate their position on ticks
Cars take penalty time which means they sleep for some amount of ticks

Moose move in behavior (make it up)

Pot holes might move (make it up)

--> In future version cars might have some intelligence <--

## World

World receives "initialize"
World reads and instantiates Moose and Pot-holes from Map.
World waits for Cars to register and creates cars.
World enters processing loop
* Ticks sent to all sims
* Position is returned.
* Collision are calculated and returned
* A list of all objects, position and collision is sent back to driver.


## Game Play

World is setup. Cars Register
Go
Up to 5 cars drive around


Now the game... 




# SETUP

Set Grid size
A set of Moose and Pot-holes in a list
Send them to the server.
Create a live view of them
Receive updates of the new positions (and collision)


Object(Car, Moose, PotHole), Position, Status: (Normal, Collision)