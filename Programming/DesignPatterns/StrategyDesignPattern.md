# Strategy Design Pattern

- - - -

## Table of Contents

* [Components](https://github.com/Mr-Bally/DevNotes/blob/main/Programming/DesignPatterns/StrategyDesignPattern.md#components)
* [Method](https://github.com/Mr-Bally/DevNotes/blob/main/Programming/DesignPatterns/StrategyDesignPattern.md#method)
* [Why is it good?](https://github.com/Mr-Bally/DevNotes/blob/main/Programming/DesignPatterns/StrategyDesignPattern.md#why-is-it-good)

## Components

* __Context:__ Has a reference to a strategy and involks it
* __IStrategy:__ A defined interface for the strategy
* __Stragegy:__ A concrete implementation of the interface strategy

For example, the context calls `IStrategy.GetTax(Order order)` for which there are multiple implementations `UkSalesTaxStrategy`, `UsaSalesTaxStrategy`.

## Method

* Idea is to select the most appropriate implementation of the strategy at runtime based on the input and without having to extend the class
* The context should not know the concrete implementation details of the strategy as it only uses the interface
* This is based on the behavioural design pattern

## Why is it good?

* Leads to a more extensible object oriented and dynamic implementation
* Easily add new strategies without affecting new ones
* Cleaner approach with single responsability in mind
* Decouple context and the concrete implementation
* Makes testing easier as you can write mocked implementation to inject into your tests

### NOTE

You can use an abstract class which implements the interface with shared functionality. Then all concrete implementations inherit from the abstract base class.
Whenever you inject an interface to allow change of behaviour you are leverging the strategy pattern.
