## **Structs** 📖

Hi, welcome to swift basics, the topics we will cover here are structs.Structs are a fundamental part of Swift and offer various advantages over classes. Here’s a breakdown of the key points about structs along with some exercises to reinforce the concepts:

- **Performance:** Structs are stored in the stack memory, making them fast to access.
- **Value Types:** Structs are value types, meaning they are copied when assigned to a new variable or passed to a function.
- **Initialization:** Structs have an implicit initializer, but you can define custom initializers to suit your needs.
- **Immutability:** Structs can be immutable (using let properties) or mutable (using var properties).

## Exercise Time 🚀

### Exercise 1: **Immutable Structs:**

1. Create an instance of UserModel and print its properties.
2. Try to modify the properties of UserModel instance. What happens?
    
    ```swift
    struct UserModel {
        let name: String
        let isPremium: Bool
    }
    ```
    

### Exercise 2: **Mutable Structs:**

1. Create an instance of UserModel2 and print its properties.
2. Use a method to mutate the isPremium property of the UserModel2 instance.
    
    ```swift
    struct UserModel2 {
        let name: String
        var isPremium: Bool
    }
    ```
    

### Exercise 3: **Immutable Struct with Method:**

1. Create an instance of UserModel3 and use the method markUserAsPremium to mark the user as premium.

```swift
struct UserModel3 {
    let name: String
    let isPremium: Bool
    
    func markUserAsPremium(newValue: Bool) -> UserModel3 {
        UserModel3(name: name, isPremium: newValue)
    }
}
```

### Exercise 4: **Mutable Struct with Private Setter:**

1. Create an instance of UserModel4 and use the mutating methods to update the isPremium property.
2. Create a tuple and pass it to the function.
    
    ```swift
    struct UserModel4 {
        let name: String
        private(set) var isPremium: Bool
        
        mutating func markUserAsPremium() {
            isPremium = true
        }
        
        mutating func updateIsPremium(newValue: Bool) {
            isPremium = newValue
        }
    }
    ```
