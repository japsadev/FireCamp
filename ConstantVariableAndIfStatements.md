## Constant, Variable and If Statements 📖

Hi, welcome to swift basics, the topics we will cover here are constant, variable and if statements.

## Usage 🔨

### Constant and Variable

```swift
// Constant
let someConstant: Bool = true

// Variable
var someVariable: Bool = true

// Cannot assign to value: 'someConstant' is a 'let' constant
// someConstant = false

someVariable = false

var myNumber: Double = 1.1234
print(myNumber)
myNumber = 2
print(myNumber)
myNumber = 234870234
print(myNumber)
myNumber = 1
print(myNumber)
myNumber = 458
```

### If Statements

```swift
// if statements

var userIsPremium: Bool = false

if userIsPremium == true {
    print("1 - user is premium")
} else {
    print("1.1 - user is NOT premium")
}

if userIsPremium {
    print("2 - user is premium")
}

if userIsPremium == false {
    print("3 - user is NOT premium")
}

if !userIsPremium {
    print("4 - user is NOT premium")
}
```

## Exercise Time 🚀

### Exercise 1: **Constants ve Variables**

1. Create a Boolean constant and set its value to true. Try to change this constant and explain what happens.
    
    ```swift
    let constantBoolean: Bool = true
    // constantBoolean = false  // This line gives an error because constantBoolean is a constant and cannot be changed.
    ```
    
2. Create a Boolean variable and set its value to true. Change the value of this variable to false.
    
    ```swift
    var variableBoolean: Bool = true
    variableBoolean = false
    ```
    
3. Create a Double variable and set its initial value to 3.14. Then change the value of this variable to 10.0, 0.99 and 100.12345 respectively. Print the value after each change.
    
    ```swift
    var myDouble: Double = 3.14
    print(myDouble)
    myDouble = 10.0
    print(myDouble)
    myDouble = 0.99
    print(myDouble)
    myDouble = 100.12345
    print(myDouble)
    ```
    
4. Write the following Swift code and explain what each line does:
    
    ```swift
    let pi: Double = 3.14159
    var radius: Double = 5.0
    var area: Double = pi * radius * radius
    print(area)
    radius = 10.0
    area = pi * radius * radius
    print(area)
    ```
    

### Exercise 2: If Statements

1. Create a Boolean variable and set its initial value to false. Write an if statement using this variable and print a message if the variable is true and another message if it is false.
    
    ```swift
    var isLoggedIn: Bool = false
    if isLoggedIn {
        print("User logged in")
    } else {
        print("User not logged in")
    }
    ```
    
2. Create an Integer variable that controls the age of the user. Write an if statement using this variable:
- If the age is 18 or older, print the message "User is an adult".
- If the age is less than 18, print the message "User is a minor".
    
    ```swift
    var userAge: Int = 20
    if userAge >= 18 {
        print("User adult")
    } else {
        print("User is a minor")
    }
    ```
    
3. Write an if statement using a Boolean variable:
- If the variable is true, print the message "Active user".
- If not, print the message "Inactive user".
- Do the same check with the ! operator instead of the == operator.
    
    ```swift
    var isActive: Bool = true
    if isActive {
        print("Active user")
    } else {
        print("Inactive user")
    }
    
    if !isActive {
        print("Inactive user")
    }
    ```
    
4. Write the following Swift code and explain what each line does:
    
    ```swift
    var isStudent: Bool = true
    if isStudent {
        print("1 - User is a student")
    } else {
        print("1.1 - User is not a student")
    }
    
    isStudent = false
    if !isStudent {
        print("2 - User is not a student")
    }
    ```
    

## Exercise Solutions 🔥

### Exercise 1.4: Swift code and explain

```swift
let pi: Double = 3.14159 // Creates a Double constant and assigns it to pi.
var radius: Double = 5.0 // Creates a Double variable and assigns it an initial value of 5.0.
var area: Double = pi * radius * radius // Calculates the area and assigns it to the area variable.
print(area) // Prints the calculated area.
radius = 10.0 // Changes the value of the radius variable to 10.0.
area = pi * radius * radius // Calculates the new area and assigns it to the area variable.
print(area) // Prints the new calculated area.
```

### Exercise 2.4: Swift code and explain

```swift
// Create a Boolean variable isStudent and set its initial value to true.
var isStudent: Bool = true

// The if statement checks the value of the variable isStudent.
if isStudent {
    // If isStudent is true, this line is executed and the message is printed.
    print("1 - User student")
} else {
    // If isStudent is false, this line is executed and the message is printed.
    print("1.1 - User is not a student")
}

// Changing the value of the variable isStudent to false.
isStudent = false

// The if statement checks the inverse value of isStudent (true if false, false if true).
if !isStudent {
    // If !isStudent is true (i.e. isStudent is false), this line is executed and the message is printed.
    print("2 - User is not a student")
}
```
