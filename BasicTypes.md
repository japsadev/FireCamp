## Basics Types 📖

Hello, welcome to swift basics, the topics we will cover here are basic variable types

## Usage 🔨

### String

```swift
// String is "regular text"
let myFirstItem: String = "Hello, world!"

// Reference previously created objects
let myTitle = myFirstItem
```

### Bool

```swift
// Boolean (aka Bool) is true or false
let mySecondItem: Bool = true
let myThirdItem: Bool = false
```

### Do not do!

```swift
let myFourthItem: String = "true"
```

### Type-safety

```swift
// Swift is a type-safe language
let myFifthItem: Bool = true
let mySixthItem: String = "Hello, world!"
let mySeventhItem = "Hello, world!"
```

### Date

```swift
let myFirstDate: Date = Date()
```

### Number can be Int, Double, CGFloat & more

### Integer

```swift
// Int is a whole Integer
let myFirstNumber: Int = 1
```

### Double

```swift
// Use Double for math
let mySecondNumber: Double = 1.0
```

### CGFloat

```swift
// Use CGFloat for UI
let myThirdNumber: CGFloat = 1.0
```

## Exercise Time 🚀

### Exercise 1: String and Bool

1. Create a variable that stores the username as a String value and then reference this variable with a new variable.
    
    ```swift
    let username: String = "Japsa"
    let userReference = username
    ```
    
2. Create two Boolean variables: one to determine whether the user is logged in (true or false) and one to determine whether the user is an administrator (true or false).
    
    ```swift
    let isLoggedIn: Bool = true
    let isAdmin: Bool = false
    ```
    
3. Try to assign a String variable to a Boolean variable. Explain what happens in this case.
    
    ```swift
    // let invalidAssignment: Bool = "true" // error.
    ```
    

### Exercise 2: **Date**

1. Create a variable that stores the current date and time and use this variable to subtract only the year.

```swift
let currentDate: Date = Date()
let calendar = Calendar.current
let year = calendar.component(.year, from: currentDate)
```

### Exercise 3: **Number: Int, Double, CGFloat**

1. Create an Int variable and increment it by 10. Assign the result to a new variable.
    
    ```swift
    let myInt: Int = 5
    let increasedInt = myInt + 10
    ```
    
2. Create a Double variable and multiply it by 2.5. Assign the result to a new variable.
    
    ```swift
    let myDouble: Double = 2.0
    let multipliedDouble = myDouble * 2.5
    ```
    
3. Create two CGFloat variables, one 3.5, the other 4.2. Add these two values and assign the result to a new variable.
    
    ```swift
    let firstCGFloat: CGFloat = 3.5
    let secondCGFloat: CGFloat = 4.2
    let sumOfCGFloats = firstCGFloat + secondCGFloat
    ```
    
4. Write the following Swift code and explain what each line does:
    
    ```swift
    let myNumber: Int = 10
    let myDouble: Double = 20.5
    let sum = Double(myNumber) + myDouble
    ```
    

## Exercise Solutions 🔥

### Exercise 3.4

```swift
let myNumber: Int = 10   // Creates an integer value and assigns it to the myNumber variable.
let myDouble: Double = 20.5  // Creates a decimal value and assigns it to the variable myDouble.
let sum = Double(myNumber) + myDouble  // Converts myNumber to Double and sums it with myDouble.
```
