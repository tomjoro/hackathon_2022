# hackathon_2022

## Time and Audience
9:00 - 14:00 (5 hours) and one hour for lunch. for that' 4. 
One hour to come together so that's 3. 

Some coders are very experienced and some are new.

It's not a lot of time, so either we setup a framework first (or specifications) or we'll have to limit what we do.

Teams need to be composed of both beginning and advanced codes so we have a good mix.

We don't have a lot of time.

## Goal

Learn some Elixir and have some fun together. Do something different than typical work.
Have something to show.
Play.

## Learning Elixir

### Resources
Presentation to Talented with quiz.
YouTube Video.
We could split into groups and make Elixir training.
We could split into groups and do a project.
We could listen to a boring lecture.

### Key Concepts
Immutability
No classes, just MFA.
Modules are just names with periods. Everything is flat.
There are anonymous functions
Closures and functions are all immutable

### Data and Data Types
Integer, String, List, Map and Struct (a type of Map)

### Libraries

Enum will move the world
List
String

### Processes
Makes the world go round.

## Project

Would be great to explore process concepts and process state.
Messaging. 
LiveView.
I wish we could do a clustered, but that's probably too much work.
Working as separate teams makes it a bit difficult to work together - but they could be separate applications in a single github.
And people could keep pushing their updates and we could run it. 
Or we could try to do it distributed. 

### Description

A process holds a 256 x 256 grid. 
* There are fixed objects on this grid called PotHoles. 
* A car can be at a position with a designation (registration)
* A car has a velocity and direction.


Team 1 (Display team): Given this, every time it changes display it in live view.
Use this link from Elixir "Mato" as an example of how to do it.

Team 2: Drive CPU team: Create cars and register them with the engine. Send messages to the cars to tell them to drive.
You will receive a message if you are approaching a PotHole so you must tell your car to change course or you will fall in.
You will receive messages if another car is within some radius.

Team 3: Game engine. Run the simulation. Receive car registrations and place them on the grid. 
Receive car speed and direction commands and run a tick or otherwise simulation to update positions.
If another car is in radius warn the car. If a pothole is within radius warn the car.
If a car fall in a hole or crashes into another car assess damage based on speed.
Notify the car insurer of the damage and get a claim number.
Notify the car owner of damage and give it a claim number.

Team 4: Insurance.
Before you drive you need insurance
Buy insurance for some amount of time.
If you car has damage use insurance to fix it.
There maybe multiple insurers so you have to find the best offer.

============

Final stage: Everyone drives their car? How? some sort of input mechanism for many cars is needed.