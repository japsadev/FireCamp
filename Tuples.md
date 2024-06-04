## Tuples 📖

Hi, welcome to swift basics, the topics we will cover here are tuples. Tuples in Swift are a powerful feature that allow you to group multiple values into a single compound value. They are particularly useful when you want to return multiple values from a function.

## 1.**Basic Tuples:**

Tuples can contain any number of elements and each element can be of different types.

You can access the elements of a tuple using index numbers starting from zero or by naming each element.

## 2.**Returning Tuples from Functions:**

Functions in Swift are limited to returning a single value. Using tuples, you can return multiple values as a single compound value.

You can define a tuple with named elements, which makes it easier to understand and use the returned values.

## Usage 🔨

```swift
var userName: String = "Hello"
var userIsPremium: Bool = false
var userIsNew: Bool = true

func getUserName() -> String {
    userName
}

func getUserIsPremium() -> Bool {
    userIsPremium
}

// Function returning a tuple with unnamed elements
func getUserInfo2() -> (String, Bool) {
    let name = getUserName()
    let isPremium = getUserIsPremium()
    return (name, isPremium)
}

let info1 = getUserInfo2()
let name1: String = info1.0  // Accessing tuple elements by index

// Function returning a tuple with named elements
func getUserInfo3() -> (name: String, isPremium: Bool) {
    let name = getUserName()
    let isPremium = getUserIsPremium()
    return (name, isPremium)
}

let info2 = getUserInfo3()
let name2 = info2.name  // Accessing tuple elements by name

// Function returning a tuple with multiple named elements
func getUserInfo4() -> (name: String, isPremium: Bool, isNew: Bool) {
    return (userName, userIsPremium, userIsNew)
}

func doSomethingWithUserInfo(info: (name: String, isPremium: Bool, isNew: Bool)) {
    print("User: \(info.name), Premium: \(info.isPremium), New: \(info.isNew)")
}

let info = getUserInfo4()
doSomethingWithUserInfo(info: info)
```

## Exercise Time 🚀

### Exercise 1: **Basic Tuple Creation and Access:**

1. Create a tuple named person with three elements: a String representing the name, an Int representing the age, and a Bool representing whether the person is employed.
2. Print each element of the tuple.
    
    ```swift
    let person = (name: "John", age: 30, isEmployed: true)
    print("Name: \(person.name), Age: \(person.age), Employed: \(person.isEmployed)")
    ```
    

### Exercise 2: **Function Returning Tuple:**

1. Write a function named getBookDetails that returns a tuple containing the title, author, and number of pages of a book.
2. Call the function and print each detail of the book.
    
    ```swift
    func getBookDetails() -> (title: String, author: String, pages: Int) {
        return ("Swift Programming", "Apple Inc.", 500)
    }
    
    let book = getBookDetails()
    print("Title: \(book.title), Author: \(book.author), Pages: \(book.pages)")
    ```
    

### Exercise 3: **Updating Tuple Values:**

1. Create a mutable tuple named car with three elements: a String representing the make, a String representing the model, and an Int representing the year.
2. Update the year of the car and print the updated tuple.
    
    ```swift
    var car = (make: "Toyota", model: "Corolla", year: 2018)
    car.year = 2021
    print("Car: \(car.make) \(car.model), Year: \(car.year)")
    ```
    

### Exercise 4: **Passing Tuples to Functions:**

1. Write a function named displayPersonInfo that takes a tuple with named elements (name: String, age: Int, isEmployed: Bool) as a parameter and prints the information.
2. Create a tuple and pass it to the function.
    
    ```swift
    func displayPersonInfo(person: (name: String, age: Int, isEmployed: Bool)) {
        print("Name: \(person.name), Age: \(person.age), Employed: \(person.isEmployed)")
    }
    
    let personInfo = (name: "Alice", age: 28, isEmployed: false)
    displayPersonInfo(person: personInfo)
    ```
    

### Exercise 5: **Complex Tuples:**

1. Create a tuple named student with nested tuples: a String for the name, a tuple containing the String major and the Int year, and a Bool indicating whether the student is on a scholarship.
2. Print each element including the nested tuple.
    
    ```swift
    let student = (name: "Bob", details: (major: "Computer Science", year: 2), onScholarship: true)
    print("Name: \(student.name), Major: \(student.details.major), Year: \(student.details.year), Scholarship: \(student.onScholarship)")
    ```
