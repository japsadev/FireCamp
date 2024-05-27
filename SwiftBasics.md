## Swift Basics 📖

Hi, welcome to swift basics, the topics we will cover here are basic variable creation, print function, comment line and naming conventions.

## Usage 🔨

### Create First Variable

```swift
var greeting = "Think Different"

print(greeting) // Think Different
```

### Comment Types

```swift
// This is a single-line comment

// These are multiple single-line comments
// This is a comment
// and this is some more info

/*
 This is a multi-line comment
 that goes to
 mutliple lines!
 */
```

### Naming Conventions

```swift
// Camel Case - CORRECT!
// The first word is lowercased and then the first character in every following word is uppercased.

let firstGreeting = "Hello, world!"
let thisIsMyFirstGreeting = "Hello, world!"

// wrong
let thisismysecondgreeting = "Hello, world!"

// Snake Case - wrong
let this_is_what_snake_case_looks_like = "Hello, world!"

// Pascal Case - wrong
let ThisIsWhatPascalCaseLooksLike = "Hello, world!"

// Camel Case - right
let thisIsWhatCamelCaseLooksLike = "Hello, world!"

```

## Exercise Time 🚀

### Exercise 1: Variables and Printing

1. Create variables and print them to the screen.

```swift
var stringType: String = "Hello World" 
print(stringType) // Hello World
```

### Exercise 2: Comments

1. Comment each line of Swift code you write and add comments explaining what it does.

```swift
import Foundation

// This variable holds a greeting message
var greeting = "Hello, playground"

// Prints the greeting message 5 times
for _ in 1...5 {
    print(greeting)
}

/*
 This is a multi-line comment.
 This comment gives information about the operation of the programme.
 may provide additional information.
 */

```

### Exercise 3: Naming Conventions

1. Rename misnamed variables in the correct camel case format.

```swift
let wrongexample = "This is a wrong example"
let another_wrong_example = "This is a wrong example"

//Rename the above variables in the correct camel case format.
```

## Exercise Solutions 🔥

### Exercise 3.1: Correctly Naming Misnamed Variables

```swift
// // Incorrectly named variables
let wrongexample = "This is a wrong example"
let another_wrong_example = "This is a wrong example"

// // Variables named in the correct camel case format
let wrongExample = "This is a wrong example"
let anotherWrongExample = "This is a wrong example"

```
