## Protocols in Swift 📖

In Swift, protocols are used to define a blueprint of methods, properties, and other requirements that suit a particular task or piece of functionality. Classes, structs, and enums can conform to protocols to provide the actual implementation of these requirements.

## Protocols

A protocol defines a set of rules or requirements that a type must adhere to. This is similar to interfaces in other programming languages.

```swift
protocol EmployeeHasAName {
    var name: String { get }
}
```

In this example, the `EmployeeHasAName` protocol requires any conforming type to have a `name` property of type `String`.

## Structs

Structs are value types that can conform to protocols. When a struct conforms to a protocol, it must implement all the properties and methods defined in the protocol.

```swift
struct EmployeeModel: EmployeeHasAName {
    let title: String
    let name: String
}
```

Here, the `EmployeeModel` struct conforms to the `EmployeeHasAName` protocol by providing a `name` property.

## Using Protocols and Structs

You can use the protocol to define a common interface for different types, and then use structs (or classes) to provide concrete implementations of this interface.

```swift
let employee = EmployeeModel(title: "Manager", name: "John Doe")
print(employee.name)  // Output: John Doe
print(employee.title) // Output: Manager
```

## Exercise Time 🚀

### Exercise 1: **Create a Protocol and Struct**

1. Define a protocol `Vehicle` with a `model` property of type `String`.
2. Create a struct `Car` that conforms to the `Vehicle` protocol and has additional properties like `make` and `year`.

```swift
protocol Vehicle {
    var model: String { get }
}

struct Car: Vehicle {
    let model: String
    let make: String
    let year: Int
}

let car = Car(model: "Model S", make: "Tesla", year: 2021)
print(car.model)
print(car.make)
print(car.year)
```

### Exercise 2: **Extend the Protocol**

1. Extend the `Vehicle` protocol to include a method `description` that returns a string.
2. Implement this method in the `Car` struct to return a formatted string describing the car.

```swift
protocol Vehicle {
    var model: String { get }
    func description() -> String
}

struct Car: Vehicle {
    let model: String
    let make: String
    let year: Int

    func description() -> String {
        return "\(year) \(make) \(model)"
    }
}

let car = Car(model: "Model S", make: "Tesla", year: 2021)
print(car.description())

```

### Exercise 3: **Create Another Struct**

1. Create another struct `Bike` that conforms to the `Vehicle` protocol.
2. Ensure it has properties like `model` and `type` (e.g., mountain, road).

```swift
struct Bike: Vehicle {
    let model: String
    let type: String

    func description() -> String {
        return "\(type) bike: \(model)"
    }
}

let bike = Bike(model: "Trek 3700", type: "Mountain")
print(bike.description())
```

### Exercise 4: Using Protocols in Functions

1. Write a function that takes any type conforming to `Vehicle` and prints its description.

```swift
func printVehicleDescription(vehicle: Vehicle) {
    print(vehicle.description())
}

let car = Car(model: "Model S", make: "Tesla", year: 2021)
let bike = Bike(model: "Trek 3700", type: "Mountain")

printVehicleDescription(vehicle: car)
printVehicleDescription(vehicle: bike)
```
