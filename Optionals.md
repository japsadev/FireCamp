## Optionals 📖

Hi, welcome to swift basics, the topics we will cover here are optionals. Options can save our lives if values are empty. We can say that it is to say what value will be assigned instead of empty data.

## Usage 🔨

```swift
// "There is always a value and it is a Boolean"
let myBool: Bool = false

// "We don't know if there is a value, but if there is, it is a Boolean"
var myOtherBool: Bool? = nil

//print(myOtherBool)
//myOtherBool = true
//print(myOtherBool)
//myOtherBool = false
//print(myOtherBool)
//myOtherBool = nil
//print(myOtherBool)
```

### Nil coalescing operator

```swift
let newValue: Bool? = myOtherBool

// "The value of myOtherBool (if there is one), otherwise false"
let newValue2: Bool = myOtherBool ?? false

print("New value 2: \(newValue2.description)")

var myString: String? = "Hello, world!"

print(myString ?? "There is no value!")

myString = "New text!"
print(myString ?? "There is no value!")

myString = nil

print(myString ?? "There is no value!")

//let newString = myString ?? "some default value"
```

### If-let

```swift
var userIsPremium: Bool? = nil

func checkIfUserIsPremium() -> Bool? {
    return userIsPremium
}

func checkIfUserIsPremium2() -> Bool {
    return userIsPremium ?? false
}

let isPremium = checkIfUserIsPremium2()

// If-let
// When if-let is successful, enter the closure
func checkIfUserIsPremium3() -> Bool {
    
    // If there is a value, let newValue equal that value
    if let newValue = userIsPremium {
        // Here we have access to the non-optional value
        return newValue
    } else {
        return false
    }
}

func checkIfUserIsPremium4() -> Bool {
    if let newValue = userIsPremium {
        return newValue
    }
    
    return false
}

func checkIfUserIsPremium5() -> Bool {
    if let userIsPremium {
        return userIsPremium
    }
    
    return false
```

### Guard-let

```swift
var userIsPremium: Bool? = nil

func checkIfUserIsPremium() -> Bool? {
    return userIsPremium
}

func checkIfUserIsPremium2() -> Bool {
    return userIsPremium ?? false
}

let isPremium = checkIfUserIsPremium2()

// Guard
// When a guard is a failure, enter the closure
func checkIfUserIsPremium6() -> Bool {
    
    // Make sure there is a value
    // If there is, let newValue equal that value
    // Else (otherwise) return out of the function
    guard let newValue = userIsPremium else {
        return false
    }
    
    // Here we have access to the non-optional value
    return newValue
}

func checkIfUserIsPremium7() -> Bool {
    guard let userIsPremium else {
        return false
    }
    
    return userIsPremium
}

```

### Layered if-let

```swift
func checkIfUserIsSetUp3() -> Bool {
    if let userIsNew {
        // userIsNew == Bool
        
        if let userDidCompleteOnboarding {
            // userDidCompleteOnboarding == Bool
            
            if let userFavoriteMovie {
                // userFavoriteMovie == String
                return getUserStatus(
                    userIsNew: userIsNew,
                    userDidCompleteOnboarding: userDidCompleteOnboarding,
                    userFavoriteMovie: userFavoriteMovie
                )
            } else {
                // userFavoriteMovie == nil
                return false
            }
            
        } else {
            // userDidCompleteOnboarding == nil
            return false
        }
    } else {
        // userIsNew == nil
        return false
    }
}
```

### Layered Guard-let

```swift
func checkIfUserIsSetUp4() -> Bool {
    guard let userIsNew else {
        // userIsNew == nil
        return false
    }
    // userIsNew == Bool
    
    guard let userDidCompleteOnboarding else {
        // userDidCompleteOnboarding == nil
        return false
    }
    // userDidCompleteOnboarding == Bool

    guard let userFavoriteMovie else {
        // userFavoriteMovie == nil
        return false
    }
    // userFavoriteMovie == String

    return getUserStatus(
        userIsNew: userIsNew,
        userDidCompleteOnboarding: userDidCompleteOnboarding,
        userFavoriteMovie: userFavoriteMovie
    )
}

func checkIfUserIsSetUp5() -> Bool {
    guard let userIsNew else {
        return false
    }
    
    guard let userDidCompleteOnboarding else {
        return false
    }

    guard let userFavoriteMovie else {
        return false
    }

    return getUserStatus(
        userIsNew: userIsNew,
        userDidCompleteOnboarding: userDidCompleteOnboarding,
        userFavoriteMovie: userFavoriteMovie
    )
}

```

### Optional chaining

```swift
func getUsername() -> String? {
    return "test"
}

func getTitle() -> String {
    return "title"
}

func getUserData() {
    
    
    let username: String? = getUsername()
    
    // "I will get the count if the username is not nil"
    let count: Int? = username?.count
    
    let title: String = getTitle()
    
    // "I will get the count always"
    let count2 = title.count
    
    
    
    // If username has a value, and first character in username has a value, then return the value of isLowercase
    // Optional chaining
    let firstCharacterIsLowercased = username?.first?.isLowercase ?? false
    
    // "If will get the count because I know 100% that username is not nil"
    // This will crash your application if username is nil!
    let count3: Int = username!.count

}

// safely unwrap an optional
// nil coalscing
// if-let
// guard

// explicitly unwrap optional
// !

```

## Exercise Time 🚀

### Exercise 1: **Basic Optional Handling**

1. **Creating Optionals:**
    1. Declare an optional String variable named optionalString and assign it a value of nil.
    2. Print the value of optionalString using optional binding (if-let).
        
        ```swift
        var optionalString: String? = nil
        
        if let value = optionalString {
            print(value)
        } else {
            print("optionalString is nil")
        }
        ```
        
2. **Assigning Values to Optionals:**
    1. Assign a value to optionalString and print it using optional binding again.
        
        ```swift
        optionalString = "Hello, Swift!"
        
        if let value = optionalString {
            print(value)
        } else {
            print("optionalString is nil")
        }
        ```
        
3. **Using Nil-Coalescing Operator:**
    1. Use the nil-coalescing operator to print the value of optionalString, providing a default value of “Default Value”.
        
        ```swift
        print(optionalString ?? "Default Value")
        ```
        

### Exercise 2: **Optional Functions**

1. **Function Returning Optional:**
    1. Write a function named findUser that takes a String parameter and returns an optional String. If the input string is “admin”, return “Admin User”, otherwise return nil.
        
        ```swift
        func findUser(username: String) -> String? {
            if username == "admin" {
                return "Admin User"
            } else {
                return nil
            }
        }
        
        let user = findUser(username: "admin")
        print(user ?? "User not found")
        ```
        
2. **Using Guard Statement:**
    1. Modify the findUser function to use a guard statement to check if the username is “admin”.
        
        ```swift
        func findUser(username: String) -> String? {
            guard username == "admin" else {
                return nil
            }
            return "Admin User"
        }
        
        let user = findUser(username: "guest")
        print(user ?? "User not found")
        ```
        
3. **Chaining Optionals:**
    1. Write a function named getFirstCharacter that takes an optional String and returns an optional Character which is the first character of the string. Use optional chaining to implement this function.
        
        ```swift
        func getFirstCharacter(of string: String?) -> Character? {
            return string?.first
        }
        
        let firstChar = getFirstCharacter(of: "Hello")
        print(firstChar ?? "No character")
        ```
