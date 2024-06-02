## Functions 📖

Hi, welcome to swift basics, the topics we will cover here are functions. Functions allow us to perform certain operations within a certain field. Its main use is to avoid code clutter for repetitive operations.

## Usage 🔨

### Create Functions

```swift
func myFirstFunction() {
    print("MY FIRST FUNCTION CALLED")
    mySecondFunction()
    myThirdFunction()
}

func mySecondFunction() {
    print("MY SECOND FUNCTION CALLED")
}

func myThirdFunction() {
    print("MY THIRD FUNCTION CALLED")
}

myFirstFunction()
```

### **Functions Returning**

```swift
func getUserName() -> String {
    let username: String = "Japsa"
    return username
}

func checkIfUserIsPremium() -> Bool {
    return false
}

let name: String = getUserName()
```

### **Functions with Conditions**

```swift
showFirstScreen()

func showFirstScreen() {
    var userDidCompleteOnboarding: Bool = false
    var userProfileIsCreated: Bool = true
    let status = checkUserStatus(didCompleteOnboarding: userDidCompleteOnboarding, profileIsCreated: userProfileIsCreated)
    
    if status == true {
        print("SHOW HOME SCREEN")
    } else {
        print("SHOW ONBOARDING SCREEN")
    }
}

func checkUserStatus(didCompleteOnboarding: Bool, profileIsCreated: Bool) -> Bool {
    if didCompleteOnboarding && profileIsCreated {
        return true
    } else {
        return false
    }
}

func doSomethingElse(someValue: Bool) {
    
}
```

### **Functions with Parameters**

```swift
let number1 = 5
let number2 = 8

func calculateNumbers() -> Int {
    return number1 + number2
}

func calculateNumbers(value1: Int, value2: Int) -> Int {
    return value1 + value2
}

let result1 = calculateNumbers()
let result2 = calculateNumbers(value1: number1, value2: number2)

var calculatedNumber: Int {
    return number1 + number2
}

```

## Exercise Time 🚀

### Exercise 1: **Basic Function Creation**

1. **Create a Function that Prints a Message:**
    
    ```swift
    //Write a function named printWelcomeMessage that prints “Welcome to Swift Programming!” when called.
    
    func printWelcomeMessage() {
        print("Welcome to Swift Programming!")
    }
    
    printWelcomeMessage()  // Output: Welcome to Swift Programming!
    ```
    
2. **Function with Parameters:**
    
    ```swift
    //Write a function named greetUser that takes a String parameter called name and prints “Hello, name!”.
    
    func greetUser(name: String) {
        print("Hello, \(name)!")
    }
    
    greetUser(name: "Kyria")  // Output: Hello, Kyria!
    ```
    
3. **Function with Return Value:**
    
    ```swift
    //Write a function named addNumbers that takes two Int parameters and returns their sum.
    
    func addNumbers(a: Int, b: Int) -> Int {
        return a + b
    }
    
    let sum = addNumbers(a: 3, b: 5)
    print(sum)  // Output: 8
    ```
    

### Exercise 2: **Function Composition and Call Order**

1. **Chain Function Calls:**
    
    ```swift
    //Write three functions named firstFunction, secondFunction, and thirdFunction. Make firstFunction call the other two functions in order and print appropriate messages in each function.
    
     func firstFunction() {
        print("First function called")
        secondFunction()
        thirdFunction()
    }
    
    func secondFunction() {
        print("Second function called")
    }
    
    func thirdFunction() {
        print("Third function called")
    }
    
    firstFunction()
    // Output:
    // First function called
    // Second function called
    // Third function called
    ```
    

### Exercise 3: **Functions with Conditional Logic**

1. **Check if Number is Even:**
    
    ```swift
    
    //Write a function named isEven that takes an Int parameter and returns true if the number is even and false otherwise.
    
    func isEven(number: Int) -> Bool {
        return number % 2 == 0
    }
    
    print(isEven(number: 4))  // Output: true
    print(isEven(number: 7))  // Output: false
    ```
    
2. **Calculate Area of a Circle:**
    
    ```swift
    //Write a function named calculateArea that takes a Double parameter representing the radius and returns the area of the circle.
    
    func calculateArea(radius: Double) -> Double {
        let pi = 3.14159
        return pi * radius * radius
    }
    
    let area = calculateArea(radius: 5.0)
    print(area)  // Output: 78.53975
    ```
    

### Exercise 4: **Computed Properties**

1. **Computed Property for Sum:**
    
    ```swift
    //Define two global variables num1 and num2. Create a computed property sum that returns the sum of num1 and num2.
    
    var num1: Int = 10
    var num2: Int = 20
    
    var sum: Int {
        return num1 + num2
    }
    
    print(sum)  // Output: 30
    ```
    
2. **Computed Property for Temperature Conversion:**
    
    ```swift
    
    //Create a global variable celsius and a computed property fahrenheit that converts the value of celsius to Fahrenheit.
    
    var celsius: Double = 25.0
    
    var fahrenheit: Double {
        return (celsius * 9/5) + 32
    }
    
    print(fahrenheit)  // Output: 77.0
    ```
    

### Exercise 5: **Function Overloading**

1. **Overload a Function:**
    
    ```swift
    //Write two overloaded functions named multiply. One should take two Int parameters and return their product. The other should take two Double parameters and return their product.
    
    func multiply(a: Int, b: Int) -> Int {
        return a * b
    }
    
    func multiply(a: Double, b: Double) -> Double {
        return a * b
    }
    
    let intProduct = multiply(a: 3, b: 4)
    let doubleProduct = multiply(a: 2.5, b: 3.0)
    
    print(intProduct)    // Output: 12
    print(doubleProduct) // Output: 7.5
    ```
