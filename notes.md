

## Notes

It would be fun to learn OTP and messaging.
Don't want to waste a lot of time with HTML

### Beginner team

For simplicity one team could use LiveView and display the "Barrier". "Crashed".
Enter your name.
Buttons for Left and right. 


### Liveview process
Team implements the Live view process that receives messages

### Game Engine

Team implements the game engine
* State is just in a map


Another team checks legality. Can't accelerate past physical capability.


### Car Process team

* Or to make it fun, each car could be a GenServer

* Receives a update position
* Returns new position


* Gets notified when there is a barrier or another car near by


### Live view map team

Displays the map each time something changes.




## Accelerate

I could setup the project. Create a game process with a set of interfaces

Register car (with pid)
Send ticks to each car -- or do they run on a timer?
Receive position messages
Send barrier alerts and other car alerts.

Setup a framework. 


How can we connect to a Phoenix channel from wscat?
https://github.com/websockets/wscat

Phoenix Liveview has a write up.



# more
https://www.rabbitmq.com/tutorials/tutorial-one-elixir.html

```
mix new rabbitmq_tutorials
cd rabbitmq_tutorials
Now let's add the dependency on the amqp library. Please modify the applications and deps sections of your mix.exs file to match below:

def application do
  [applications: [:amqp]]
end
defp deps() do
  [
    {:amqp, "~> 1.0"},
  ]
end
```



# Learn

How to code. Very quickly with some Kata.
Learn some OTP
Learn some live view

Do we want to learn messaging and rabbitMq?
