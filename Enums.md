## **Enums** 📖

Hi, welcome to swift basics, the topics we will cover here are enums. Enums (Enumerations) in Swift provide a way to define a group of related values in a single type-safe collection. Here’s an explanation of enums along with some exercises to reinforce the concepts.

## **Explanation**

- **Definition:** Enums define a group of related values under a single type.
- **Cases:** Enums consist of a set of named cases, each representing a unique value of the enum type.
- **Memory Storage:** Enums are stored in memory similarly to structs, but they are immutable and cannot be mutated.
- **Associated Values:** Enums can also have associated values, allowing additional data to be associated with each case.
- **Computed Properties:** Enums can contain computed properties, methods, and even initializers.

## Exercise Time 🚀

### Exercise 1: **Defining Enums:**

1. Define an enum called CardBrandOption with cases for three car brands: Ford, Toyota, and Honda.

```swift
enum CardBrandOption {
    case ford, toyota, honda
}
```

### Exercise 2: **Using Enums:**

1. Create instances of CarModel for different car models, each associated with a specific CardBrandOption.
2. Print out the title of the CardBrandOption associated with each car model.
    
    ```swift
    struct CarModel {
        let brand: CardBrandOption
        let model: String
    }
    
    var car1 = CarModel(brand: .ford, model: "Fiesta")
    var car2 = CarModel(brand: .ford, model: "Focus")
    var car3 = CarModel(brand: .toyota, model: "Camry")
    
    print(car1.brand.title) // Output: Ford
    print(car2.brand.title) // Output: Ford
    print(car3.brand.title) // Output: Toyota
    ```
    

### Exercise 3: **Enum with Computed Property:**

1. Extend the CardBrandOption enum with a computed property called title, which returns the string representation of each case.

```swift
enum CardBrandOption {
    case ford, toyota, honda
    
    var title: String {
        switch self {
        case .ford:
            return "Ford"
        case .toyota:
            return "Toyota"
        case .honda:
            return "Honda"
        }
    }
}
```
