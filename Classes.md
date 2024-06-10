## Classes 📖

Hi, welcome to swift basics, the topics we will cover here are classes. Classes in Swift are a fundamental part of object-oriented programming. Unlike structs, classes are reference types, which means they are stored in the heap memory and can be shared across different parts of your code. This allows classes to have behaviors such as inheritance, reference counting, and the ability to modify the same instance across different references.

## **Key Characteristics of Classes:**

- **Reference Type**: Variables that reference a class instance actually point to the same instance in memory. Changes to one reference affect all references.**:** Enums consist of a set of named cases, each representing a unique value of the enum type.
- **Heap Storage**: Class instances are stored in the heap, which makes them slower to allocate and deallocate compared to stack-allocated structs.
- **Inheritance**: Classes can inherit properties, methods, and other characteristics from another class.
- **Deinitializers**: Classes can define a deinit method that gets called just before the instance is deallocated.

## **Example: ScreenViewModel Class**

Here’s an example class that represents the view model for a screen. This class includes properties and methods to manage the state of a button on the screen.

```swift
import Foundation

class ScreenViewModel {
    let title: String
    private(set) var showButton: Bool
    
    init(title: String, showButton: Bool) {
        self.title = title
        self.showButton = showButton
    }
    
    deinit {
        // Code to run when the instance is being deallocated
    }
    
    func hideButton() {
        showButton = false
    }
    
    func updateShowButton(newValue: Bool) {
        showButton = newValue
    }
}

let viewModel: ScreenViewModel = ScreenViewModel(title: "Screen 1", showButton: true)
let value = viewModel.showButton

viewModel.hideButton()
viewModel.updateShowButton(newValue: false)
```

In the example above:

- The ScreenViewModel class has a title property and a showButton property.
- The hideButton method sets showButton to false.
- The updateShowButton method allows updating the value of showButton.
- Using let to declare viewModel ensures that while the reference to the instance doesn’t change, the properties within the instance can still be modified.

## Exercise Time 🚀

### Exercise 1: **Create a New Class**

1. Define a class UserProfile with properties username (String) and isLoggedIn (Bool). Add an initializer to set the initial values of these properties. Implement methods logIn and logOut that set isLoggedIn to true and false, respectively.

```swift
import Foundation

class UserProfile {
    let username: String
    private(set) var isLoggedIn: Bool
    
    init(username: String, isLoggedIn: Bool = false) {
        self.username = username
        self.isLoggedIn = isLoggedIn
    }
    
    func logIn() {
        isLoggedIn = true
    }
    
    func logOut() {
        isLoggedIn = false
    }
}

// Creating an instance of UserProfile
let userProfile = UserProfile(username: "john_doe")

// Print the initial state
print("Is logged in: \(userProfile.isLoggedIn)") // false

// Log in the user
userProfile.logIn()
print("Is logged in: \(userProfile.isLoggedIn)") // true

// Log out the user
userProfile.logOut()
print("Is logged in: \(userProfile.isLoggedIn)") // false
```

### Exercise 2: **Modify an Existing Instance**

1. Create an instance of UserProfile. Call the logIn and logOut methods on this instance. Print the value of isLoggedIn before and after each method call to observe the changes.

```swift
// Assuming the UserProfile class from Exercise 1

// Creating an instance of UserProfile
let user = UserProfile(username: "alice")

// Print the initial state
print("Initial login status: \(user.isLoggedIn)") // false

// Log in the user
user.logIn()
print("After login: \(user.isLoggedIn)") // true

// Log out the user
user.logOut()
print("After logout: \(user.isLoggedIn)") // false
```

### Exercise 3: **Inheritance**

1. Create a subclass of UserProfile called AdminProfile that includes an additional property accessLevel (Int). Add a method updateAccessLevel that allows updating the accessLevel. Create an instance of AdminProfile and demonstrate how you can set the username, isLoggedIn, and accessLevel properties.

```swift
class AdminProfile: UserProfile {
    private(set) var accessLevel: Int
    
    init(username: String, isLoggedIn: Bool = false, accessLevel: Int) {
        self.accessLevel = accessLevel
        super.init(username: username, isLoggedIn: isLoggedIn)
    }
    
    func updateAccessLevel(newLevel: Int) {
        accessLevel = newLevel
    }
}

// Creating an instance of AdminProfile
let admin = AdminProfile(username: "admin_jane", accessLevel: 5)

// Print the initial state
print("Username: \(admin.username)")
print("Is logged in: \(admin.isLoggedIn)")
print("Access level: \(admin.accessLevel)")

// Log in the admin
admin.logIn()
print("Is logged in after login: \(admin.isLoggedIn)")

// Update access level
admin.updateAccessLevel(newLevel: 10)
print("Updated access level: \(admin.accessLevel)")
```

### Exercise 3: **Deinitializer**

1. Add a deinit method to the UserProfile class that prints a message when the instance is deallocated. Create and destroy instances of UserProfile to see when the deinitializer gets called.

```swift
class UserProfile {
    let username: String
    private(set) var isLoggedIn: Bool
    
    init(username: String, isLoggedIn: Bool = false) {
        self.username = username
        self.isLoggedIn = isLoggedIn
    }
    
    func logIn() {
        isLoggedIn = true
    }
    
    func logOut() {
        isLoggedIn = false
    }
    
    deinit {
        print("\(username) is being deinitialized")
    }
}

// Creating and destroying an instance of UserProfile
do {
    let tempUser = UserProfile(username: "temp_user")
    print("Created user: \(tempUser.username)")
}

// tempUser goes out of scope and should be deinitialized
```
