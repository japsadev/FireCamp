# Object Oriented Programming 📖

Hi, welcome to swift basics, the topics we will cover here are object oriented programming(OOP). **Object-Oriented Programming (OOP)** is a paradigm in programming where we model software using objects. These objects are instances of classes or structures that encapsulate data and behavior.

## **1. Initialization and Deinitialization:**

- **Initialization (init):** Creating an object and adding it to memory.
- **Deinitialization (deinit):** Destroying an object and removing it from memory.

## **2. Automatic Reference Counting (ARC):**

- ARC keeps track of the number of references to each object.
- Creating an object increases the reference count.
- Destroying an object decreases the reference count.
- More objects in memory can slow down the app; hence, it’s crucial to manage object creation and destruction effectively.

## **3. Memory Management:**

- **Stack:** Fast, lower memory footprint, stores basic types, structs, enums, and arrays.
- **Heap:** Slower, higher memory footprint, stores functions, classes, and actors.
- The iPhone operates in a multi-threaded environment with each thread having its stack, but only one heap shared among threads.

## **4. Value vs. Reference Types:**

- **Value Types (Stack):** When edited, a copy of the value is created (e.g., structs, enums).
- **Reference Types (Heap):** When edited, the original object is modified through a reference (pointer) to the object in memory (e.g., classes).
- The gif I've shown below also explains it visually.

<img src="https://miro.medium.com/max/940/1*N4CTsUuCT8mu7k2YlADqxQ.gif">

## **Class vs. Struct**

## **Classes**:

- Use when you want to create objects that perform actions.
- Examples: Manager, DataService, ViewModel.
- Classes are reference types (stored in the heap).

## **Structs**:

- Use for data models and objects that are passed around.
- Examples: Data models, simple data containers.
- Structs are value types (stored in the stack).

```
Metaphor:

•	Imagine a school where classrooms (classes) have quizzes (structs).
•	A classroom represents a class where actions take place.
•	Quizzes represent structs that can be handed out and passed around.

```

## **Code Examples**:

**Struct Example:**

```swift
struct MyFirstObject {
    let title: String = "Hello, world!"
}
```

**Class Example:**

```swift
class MySecondObject {
    let title: String = "Hello, world!"
}
```

## Exercise Time 🚀

### Exercise 1: **Create a Struct:**

1. Define a struct named Book with properties title (String), author (String), and pages (Int).
2. Create an instance of the Book struct and print its properties.
    
    ```swift
    struct Book {
        let title: String
        let author: String
        let pages: Int
    }
    
    let myBook = Book(title: "Swift Programming", author: "Apple Inc.", pages: 500)
    print("Title: \(myBook.title), Author: \(myBook.author), Pages: \(myBook.pages)")
    ```
    

### Exercise 2: **Create a Class:**

1. Define a class named Person with properties name (String) and age (Int).
2. Add a method named greet() that prints a greeting message.
3. Create an instance of the Person class, call the greet() method, and print the properties.
    
    ```swift
    class Person {
        let name: String
        let age: Int
    
        init(name: String, age: Int) {
            self.name = name
            self.age = age
        }
    
        func greet() {
            print("Hello, my name is \(name) and I am \(age) years old.")
        }
    }
    
    let person = Person(name: "John", age: 30)
    person.greet()
    print("Name: \(person.name), Age: \(person.age)")
    ```
    

### Exercise 3: **Value Type Behavior:**

1. Define a struct named Rectangle with properties width and height (both Int).
2. Create an instance and copy it to another variable.
3. Modify the copy and print both the original and the modified instance to observe value type behavior.
    
    ```swift
    struct Rectangle {
        var width: Int
        var height: Int
    }
    
    var rect1 = Rectangle(width: 10, height: 20)
    var rect2 = rect1
    rect2.width = 30
    
    print("rect1: \(rect1.width) x \(rect1.height)")
    print("rect2: \(rect2.width) x \(rect2.height)")
    ```
    

### Exercise 4: **Reference Type Behavior:**

1. Define a class named Circle with a property radius (Int).
2. Create an instance and copy it to another variable.
3. Modify the copy and print both the original and the modified instance to observe reference type behavior.
    
    ```swift
    class Circle {
        var radius: Int
    
        init(radius: Int) {
            self.radius = radius
        }
    }
    
    let circle1 = Circle(radius: 15)
    let circle2 = circle1
    circle2.radius = 25
    
    print("circle1: \(circle1.radius)")
    print("circle2: \(circle2.radius)")
    ```
