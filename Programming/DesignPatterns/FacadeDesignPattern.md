# Facade Design Pattern

- - - -

## Table of Contents

* [Characteristics](https://github.com/Mr-Bally/DevNotes/blob/main/Programming/DesignPatterns/FacadeDesignPattern.md#characteristics)
* [Big Class Facade](https://github.com/Mr-Bally/DevNotes/blob/main/Programming/DesignPatterns/FacadeDesignPattern.md#big-class-facade)
* [Worker Class Facade](https://github.com/Mr-Bally/DevNotes/blob/main/Programming/DesignPatterns/FacadeDesignPattern.md#worker-class-facade)

## Characteristics

* Adds a layer of abstraction between a caller and functionality to reduce complexity for the caller
* Can be catagorised into two broad variants:
  * Big Class Facade
  * Worker Class Facade

## Big Class Facade

* In badly designed systems you may come across large classes with many different methods
  * These are sometimes called "Balls of mud" or "God" classes
* The facade is another class which sits inbetween the caller and the big class
* The facade reference a number of the methods in the large class but not all
* The facade can give these methods more meaningful names and reduce the complexity and choice for the caller
* This abstract away from direct calls and allows implementation details to change without alterations to the caller

## Worker Class Facade

* This is when you have several worker service classes where the order in which you involk them matters
* This ideally wouldn't be an issue but it can be in some systems
* The facade here would handle all the complexity (e.g. managing in what order the service classes are called)
* The caller would call a simpler method on the facade which would involk the above
