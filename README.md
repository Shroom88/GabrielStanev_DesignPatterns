# GabrielStanev_DesignPatterns
F№: 1809011299

'Vehicle on a highway' Simulator

Patterns Used:
1) Creational: Bluilder
2) Structural: Decorator
3) Behavioral: State

A console application that creates moving vehicles with radio
The Builder creates the vehicle (car/bike) with Wheels,Frame,Engine,FuelType and HorsePower.
The Decorator then links the Radio with the vehicle, prints the properties of the vehicle and radio starts playing a random song out of 5.
Then the car has two states: Slow and Fast. Both states have implenented interface IState and are overriding Speed() method
The speed is a Counter property set with a constant integer of 40 (minimal highway speed limit)
The slow state's Speed() Method indicates if the current speed of the vehicle is below 60 and switches the vehicle's state
to FastState(). If the current speed (Counter) is above 60, it decreases the speed. The FastState increases the speed.

The Builder has an abstract class 'Vehicle Builder' with create and get methods and abstract methods for 'Set()' of properties
'Vehicle' has the vehicle's properties, implements Component class from the Decorator and overrides Operation() to print the vehicle's properties. There are also the properties of the State Pattern for the movement of the vehicle and the Request method which is calling Speed() for this vehicle.
The Director class generates the vehicle by calling the Set() methods from the VehicleBuilder abstraction and returns the getVehicle() method.
Then there're the two types of vehicles: CarBuilder and BikeBuilder where I set concrete properties for the vehicle.

The Decorator Pattern uses an abstract class 'Component' with an abstract Operation() method. Class 'Decorator' implements 'Component', makes protected property, then sets the component via SetComponent(Component c) method. Overrides the Operation() method to call the Operation Method for the protected property if it is not null. The CarRadio class implements the Component class, overrides Operation to call the base.Operation();, prints out that the radio is playing and calls PlayMusic() method, which has a random 5 switch structure to print out 1 of 5 different songs.
