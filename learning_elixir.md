## Learning Elixir

### Resources
 * If you know some Clojure, Scala, etc. Elixir comes pretty easy

Presentation to Talented with quiz.
YouTube Video.
We could split into groups and make Elixir training.
We could split into groups and do a project.
We could listen to a boring lecture.
Elixir School.

### Key Concepts
Immutability
 * Is Elixir pass by reference or by value?
 * Functions are not going to COPY

No classes, just MFA.
 * Module, Function, Argument.

Freedom
  * All Modules are loaded. That's it. /lib and *.ex. 
  * Modules are just names that can have dots. File names don't matter. 

Functions can be anonymous. 
 * They look a little different and we use them lots in Enum.

There are anonymous functions
Closures and functions are all immutable

### Data and Data Types
 * Integer, String, List, Map
 * Struct (a type of Map)
 * Pattern matching "=" is not assignment

### Control
 * functions
 * if
 * cond
 * case

### Libraries

 * Enum
 * List
 * String

### Processes
 * Are how we build state
 * (seem my presentation about loops)
 * spawn(fn) or MFA

 ### Tooling
 
 * iex > h Enum. c("something.ex")
 * Almost all projects start with a "mix new".
 * mix deps.get

 Writing Elixir with a project structure is too difficult.



### State comes from loops

How to get states out
Event driven

Document first
function
