## **Arrays, Sets, and Custom Data Models in Swift** 📖

Hi, welcome to swift basics, the topics we will cover here are **Arrays, Sets, and Custom Data Models in Swift** .

## **Arrays**

Arrays are ordered collections of values. They allow you to store multiple values of the same type in a single variable. Arrays in Swift are zero-indexed, meaning the first element has an index of 0.

```swift
let apple: String = "Apple"
let orange: String = "Orange"

let fruits1: [String] = ["Apple", "Orange"]
let fruits2: [String] = [apple, orange]
let fruits3: Array<String> = [apple, orange]
```

### **Common Array Operations**

- **Count**: Get the number of elements in the array.

```swift
let count = fruitsArray.count
```

- **First and Last**: Access the first and last elements of the array.

```swift
let firstItem = fruitsArray.first
let lastItem = fruitsArray.last
```

- **Append**: Add elements to the end of the array.

```swift
fruitsArray.append("Banana")
fruitsArray.append(contentsOf: ["Banana", "Mango"])
```

- **Insert**: Insert elements at a specific index.

```swift
fruitsArray.insert("Watermelon", at: 2)
```

- **Remove**: Remove elements from the array.

```swift
if fruitsArray.indices.contains(1) {
    fruitsArray.remove(at: 1)
}
fruitsArray.removeAll()
```

## **Sets**

Sets are unordered collections of unique values. They are useful when you need to ensure that an item appears only once in a collection.

```swift
var finalFruits: [String] = ["Apple", "Orange", "Banana", "Apple"]
print(finalFruits)

var fruitsSet: Set<String> = ["Apple", "Orange", "Banana", "Apple"]
print(fruitsSet)
```

## **Tuples**

Tuples are used to group multiple values into a single compound value. They can contain values of different types.

```swift
var myTitle: String = "Hello, world!"
var myTitle2: String = "Hello, world!!!"

// Tuple
func doSomething(value: (title1: String, title2: String)) {
}

doSomething(value: (myTitle, myTitle2))
```

## **Dictionaries**

Dictionaries are collections of key-value pairs. Each value is associated with a unique key.

```swift
var myFirstDictionary: [String: Bool] = [
    "Apple": true,
    "Orange": false
]

let item = myFirstDictionary["Banana"]  // Accessing a value using a key

var anotherDictionary: [String: String] = [
    "abc": "Apple",
    "def": "Banana",
]

let item2 = anotherDictionary["abc"]
anotherDictionary["xyz"] = "Mango"  // Adding a new key-value pair
anotherDictionary.removeValue(forKey: "def")  // Removing a key-value pair
print(anotherDictionary)  // Prints ["abc": "Apple", "xyz": "Mango"]
```

## **Custom Data Models**

Custom data models allow you to create complex data structures that group related values together. In Swift, you can use structures (struct) or classes (class) to define custom data models.

```swift
struct TitlesModel {
    let title1: String
    let title2: String
}

func doSomething(value: TitlesModel) {
}

doSomething(value: TitlesModel(title1: myTitle, title2: myTitle2))
```

```swift
struct ProductModel {
    let title: String
    let price: Int
}

var myProducts: [ProductModel] = [
    ProductModel(title: "Product 1", price: 50),
    ProductModel(title: "Product 2", price: 5),
    ProductModel(title: "Product 3", price: 1),
    ProductModel(title: "Product 4", price: 50),
    ProductModel(title: "Product 5", price: 4),
    ProductModel(title: "Product 6", price: 50),
    ProductModel(title: "Product 7", price: 2),
]
```

## Exercise Time 🚀

### Exercise 1: **Create an Array of Integers**

1. Create an array of integers named numbers containing values from 1 to 10.
2. Print the count of the array.
3. Print the first and last elements.

```swift
var numbers: [Int] = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
print(numbers.count)
print(numbers.first ?? "No elements")
print(numbers.last ?? "No elements")
```

### Exercise 2: **Modify an Array**

1. Create an array of strings named colors containing some color names.
2. Append two more colors to the array.
3. Insert a color at the second position.
4. Remove the first color.

```swift
var colors: [String] = ["Red", "Green", "Blue"]
colors.append(contentsOf: ["Yellow", "Purple"])
colors.insert("Orange", at: 1)
if colors.indices.contains(0) {
    colors.remove(at: 0)
}
print(colors)
```

### Exercise 3: **Create and Use a Set**

1. Create a set of integers named uniqueNumbers with some duplicate values.
2. Print the set to show that duplicates are removed.
3. Add a new number to the set.
4. Remove a number from the set.

```swift
var uniqueNumbers: Set<Int> = [1, 2, 3, 4, 4, 5, 5]
print(uniqueNumbers)
uniqueNumbers.insert(6)
uniqueNumbers.remove(3)
print(uniqueNumbers)
```

### Exercise 4: **Custom Data Model**

1. Create a struct named Book with properties title, author, and isBestSeller.
2. Create an array of Book instances.
3. Print the titles of all best-selling books.

```swift
struct Book {
    let title: String
    let author: String
    let isBestSeller: Bool
}

var books: [Book] = [
    Book(title: "Book 1", author: "Author 1", isBestSeller: true),
    Book(title: "Book 2", author: "Author 2", isBestSeller: false),
    Book(title: "Book 3", author: "Author 3", isBestSeller: true)
]

for book in books {
    if book.isBestSeller {
        print(book.title)
    }
}
```
