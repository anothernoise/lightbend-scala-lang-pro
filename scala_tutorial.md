# Scala Tutorials

- https://github.com/Lockdain/lsl-p
- https://github.com/paulb79/scala-training/tree/master/pro-exercises
  
  

### Install the development environment (MacOS)

#### Prerequsites
 - Unix compatible shell
 - JVM 1.8 or higher
 - SBT 0.13.13 or higher

#### Install
```shell
brew cask install java
java -version
brew install scala
brew install sbt
sbt sbtVersion
```

### Scala REPL
```scala
sbt console
```
or
```scala
scala
```
All commands can be abbreviated
```scala
scala> scala:help
scala> scala:quit
```
#### Useful REPL Commands 
```scala
:cp <path> add a jar or direthe classpath 
:help [command] print this summary or command-specific help 
:history [num] show the history (optional num is commands to show)
:javap <pathIclass> disassemble a file or class name 
    options:
        -p show Java representation
        -c show disassembled bytecode
        -v show all
:load <path> load and interpret a Scala file 
:paste enter paste mode: all input up to ctrl-D compiled together :quit exit the interpreter :replay reset execution and replay all previous commands 
:reset reset the repl to its initial state, forgetting all session entries :sh <command line> run a shell command (result is implicitly => List[String]) 
:warnings show the suppressed warnings from the most recent line which had an 
```



### Working on Exercises Tool
```
• man e - Displays current exercise instructions. 
• showExerciseID - Displays the current exercise name. 
• listExercises - Lists all exercises in course. 
• nextExercise - Brings new tests and instructions into scope, while preserving your code. 
• prevExercise - Reverts tests and instructions to the previous state, while preserving your code. 
• gotoExerciseNr <ex Nr> - Jump to exercise Nr, bring in tests for that exercise while preserving code. 
• pullSo1ution - Overwrites your code with the official solution. 
• saveState - Create a snapshot of your current code. 
• restoreState <ex Id> - Restore the code from a saved snapshot. 
• savedStates - List all saved states. 
```

## Scala syntax 
- An immutable value with defined with the ```val ``` keyword
- Type Inference
    - This compilier can infer the type
    - For public API should provide the type explicity
    - Scala is staticaly typed 
- Expression oriented programming
  - A ```statement```  get executed with no return value, purely for its ```side-effects```
  - An ```expression``` gets evaluated to a value:
    - ex.: ```val v = if (1==1) "correct" "incorect"```  
  - Expression block
    - The return value of the block is last expression in the block
    - Code block expressions: ```val v = {..} ```

## OOP
- Object orientatation
  - Classes & traits:
      * Define with  ```class``` keyword
      * Class insatnce create using ```new ``` keyword
      * ```AnyRef``` keyword is used if no superclass is extended explicitly 
      * Each class get ```primary constructor``` automatically (into the body if the class)
      * Fields keep state
      * Methods provide operations (encapsulation)
      * Access modifiers declare visiability (inforamtion hiding)
      * Singleton object are first-class objects
  -  Additinal constructor
      -  the primiry constructor is created automatically
      -  Use ```def``` followed by ```this``` to define an additinal constructor
      -  int the end of primiry constructor must be called 
         -  ensures that all class parameters are initialized
        ```scala
        class Hello(message: String){
            def this() = this("Hello")
            println(message)
        }
      ```
  - Class parameters (Bytecode represenation)
      * immutable field gets compiled to 
        - Immutable Fields
            ```scala
            class Hello{
                val message = "Hello"
            }
            ```
            * ```final private ``` field
            * ```public``` getter method
            * This allow the [```uniform access principle```](https://docs.scala-lang.org/glossary/index.html#:~:text=The%20uniform%20access%20principle%20states,call%20sites%20of%20parameterless%20functions.): For the client it should make no difference whether a property is implemented through storage or through computation
            ```
        - Mutable fields
            ```scala
                class Hello{
                    var message = "Hello"
                }
            ```
            - Mutable field get compiled into
              * ```private``` field
              * ```public``` getter method
              * ```public``` setter method

            - Best Practise - Mutable or Immutable? 
                - Scala lets you pick the right tool for the job 
                - enerally, keep the API immutable 
                    - Code free of side-effects is easier to reason about 
                    - Pure functions can be tested easily 
                    - Immutable objects won't lead to concurrency issues 
                - Best practice 
                    - Prefer immutable objects 
                    - Use vars only if you have a specific use case, e.g. (in Akka) 

        - Class parameters are Not Fields
            ```scala
                class Hello(message: String)
                val hello  = new Hello("Hello")
                >hello.message
                Error: value message is not a member of Hello
            ```
            Class parameters re only constructor parameters:
              - they can be used into class body
              - they cannot be assesed from the outside


  - Methods provide operations (encapsulation)
  - Access modifiers declare visiability (inforamtion hiding)
  - Singleton object are first-class objects
  - Inheritance 
    - Single Inheritance
    - Multiple traits
- 








## Deploy (Dockenirize)
```shell

```