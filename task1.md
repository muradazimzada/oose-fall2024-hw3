
# Overview
This design outlines an object-oriented parking lot system that manages various types of parking spots and vehicles. The system differentiates between three kinds of parking spots (small, medium, and large) and ensures that only appropriate vehicles park in their designated spot sizes.

The design is modular and extendable, adhering to the principles of high cohesion and low coupling.

## Interfaces
We separate the system into interfaces and classes for better flexibility and scalability. The following interfaces define common behaviors for vehicles and parking spots.

### IParkingSpot
This interface defines the shared behavior of all parking spot types.

**Methods**:
isAvailable(): Checks if the spot is free to park.
parkVehicle(Vehicle vehicle): Parks the vehicle in the spot.
removeVehicle(): Removes a parked vehicle from the spot.

### IVehicle

This interface defines the common behavior of all vehicles in the system.

**Methods**:
getVehicleType(): Returns the type of vehicle (Motorcycle, Car, Bus).
canPark(IParkingSpot spot): Determines if the vehicle can park in the given spot based on its size.
Classes

### ParkingLot

This class is responsible for managing parking spots and vehicle allocations. It maintains a collection of parking spots of different sizes and handles the logic for finding available spots.

**Responsibilities**:
Add parking spots to the system.
Allocate available spots based on the vehicle's size.
Track availability of parking spots.
ParkingSpot (Implements IParkingSpot)
This is an abstract class that implements the IParkingSpot interface and defines common logic for parking spots. It is further extended by three specific classes for different spot types.

### SmallSpot

Spot for Motorcycles.
Implements methods to park motorcycles and check availability.

### MediumSpot

Spot for Cars.
Implements methods to handle cars.

### LargeSpot

Spot for Buses.
Handles the parking of buses.

### Vehicle (Implements IVehicle)

This is an abstract class implementing the IVehicle interface. It provides shared logic for vehicle properties and parking behavior. It is extended by specific vehicle types.

### Motorcycle

Can park in SmallSpot only.
Implements methods that allow it to check if a spot is compatible with a motorcycle.

### Car

Can park in MediumSpot.
Checks for appropriate spot size before parking.

### Bus

Can park in LargeSpot.
Similar to the others but for larger spots.

## Design Considerations

**Interface Flexibility**: The separation of interfaces for vehicles and parking spots ensures that new vehicle or spot types can be added without modifying existing code. 
This follows the open-closed principle (OCP).

**Cohesion and Responsibility**: Each class and interface has a single, well-defined role (managing parking lots, handling vehicles, managing spot allocation), leading to high cohesion. 
For example, the ParkingLot class doesn’t concern itself with the behavior of vehicles but only with the allocation of spots.

**Low Coupling**: The vehicle and spot classes are only linked through interfaces. 
This ensures that changes in one part (like adding a new vehicle type) don’t heavily impact other parts of the system, promoting low coupling.

This design provides a scalable and flexible approach to handling different types of vehicles and parking spots in the system. 
It adheres to key design principles like cohesion and coupling, ensuring the system remains maintainable as it grows.