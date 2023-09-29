# Decorator Design Pattern

- - - -

## Table of Contents

* [Characteristics](https://github.com/Mr-Bally/DevNotes/blob/main/Programming/DesignPatterns/DecoratorDesignPattern.md#characteristics)
* [When to use](https://github.com/Mr-Bally/DevNotes/blob/main/Programming/DesignPatterns/DecoratorDesignPattern.md#when-to-use)
* [.NET Use](https://github.com/Mr-Bally/DevNotes/blob/main/Programming/DesignPatterns/DecoratorDesignPattern.md#net-use)

## Characteristics

* A structural design pattern used for dynamically adding behaviour to classes
* There is component you want to extend which is defined by an interface
* Then you have a decorator which also implements this interface as well which accepts a contructor which take in an object which implements the same interface
* Allows the decorator class to act as a wrapper on the original class
* This means it can intercept any calls made for the interface defined methods and add in any extra functionality before calling the decorated class
* If desired you can wrap several decorators in one another

## When to use

* You don't own the code for the base implementation
* When you don't want to increase the complexity of the base implementation
* If you want to manipulate data going to and from a component (e.g. encrypting data)

## .NET Use

* Abstract "Stream" class
  * Concrete implementations e.g. FileStream, MemoryStream, NetworkStream
  * Decorators BufferedStream, GZipStream, CryptoStreamas they take in a concrete implementation of Stream class in their constructor
