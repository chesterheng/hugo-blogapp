+++
title = 'My Fifth Post My Fifth Post My Fifth Post'
date = 2023-11-24T09:16:52+08:00
draft = false
description = "This is a description"
image = "images/5s.webp"
imageBig = "images/5b.webp"
categories = ["general", "life", "health"]
authors = ["Jane", "Mary", "Tom"]
avatar = "images/avatar.webp"
+++

# How abstraction works?

Abstraction in object-oriented programming involves hiding the complex implementation details and showing only the necessary features of an object. 

Here, Vehicle is an abstract class with an abstract method start(). The Car and Motorcycle classes extend Vehicle and provide their specific implementation for the start() method. The Vehicle class defines a common interface displayInfo() to display information, allowing users to interact with the objects without knowing their internal complexities. This is an example of abstraction, where the details of how the methods work are hidden, providing a clear interface for usage.

```js
class Vehicle {
  constructor(type, make, model) {
    this.type = type;
    this.make = make;
    this.model = model;
  }

  displayInfo() {
    console.log(`Type: ${this.type}, Make: ${this.make}, Model: ${this.model}`);
  }

  // Abstract method to be implemented by child classes
  start() {
    throw new Error('Method start() must be implemented');
  }
}

class Car extends Vehicle {
  constructor(make, model) {
    super('Car', make, model);
  }

  start() {
    console.log(`${this.make} ${this.model} engine started.`);
  }
}

class Motorcycle extends Vehicle {
  constructor(make, model) {
    super('Motorcycle', make, model);
  }

  start() {
    console.log(`Starting the engine of ${this.make} ${this.model}.`);
  }
}

const myCar = new Car('Toyota', 'Corolla');
// Car {
//   type: 'Car',
//   make: 'Toyota',
//   model: 'Corolla',
//   __proto__: { constructor: ƒ Car(), start: ƒ start() }
// }

myCar.displayInfo(); // Output: Type: Car, Make: Toyota, Model: Corolla
myCar.start(); // Output: Toyota Corolla engine started.

const myBike = new Motorcycle('Harley Davidson', 'Sportster');
// Motorcycle {
//   type: 'Motorcycle',
//   make: 'Harley Davidson',
//   model: 'Sportster',
//   __proto__: { constructor: ƒ Motorcycle(), start: ƒ start() }
// }

myBike.displayInfo(); // Output: Type: Motorcycle, Make: Harley Davidson, Model: Sportster
myBike.start(); // Output: Starting the engine of Harley Davidson Sportster.
```