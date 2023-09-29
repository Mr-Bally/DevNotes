# Singleton Design Pattern

- - - -

## Table of Contents

* [Characteristics](https://github.com/Mr-Bally/DevNotes/blob/main/Programming/DesignPatterns/SingletonDesignPattern.md#characteristics)
* [Antipattern](https://github.com/Mr-Bally/DevNotes/blob/main/Programming/DesignPatterns/SingletonDesignPattern.md#antipattern)
* [Static classes vs Singletons](https://github.com/Mr-Bally/DevNotes/blob/main/Programming/DesignPatterns/SingletonDesignPattern.md#static-classes-vs-singletons)

## Characteristics

* A singleton is a class designed over to only ever have one or no instance at a given time
* The singleton class itself enforces this requirement
* An example could be a shared resource like a file system
* Singleton classes are created without parameters

## Antipattern

* Promotes tight coupling
* Is difficult to test
* Doesn't follow principles such as:
  * Separation of concerns
  * Single responsibility (because they are responsible for managing their lifetime instance)

> There are other ways you can achieve single responsability like static classes

## Static classes vs Singletons

* Singletons can do a number of things static classes cannot including:
  * Implement interfaces
  * Be passed into a method as an argument
  * Be assigned to variables
* Singletons also support polymorphism whereas static classes are purely procedural
* Singletons can have state whereas static classes only have access to global state
