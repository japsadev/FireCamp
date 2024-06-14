## **For-In Loops** 📖

Hi, welcome to swift basics, the topics we will cover here are **For-In Loops.** For-in loops in Swift are used to iterate over a sequence of items, such as arrays, dictionaries, ranges, and other collections. They allow you to execute a block of code multiple times, once for each item in the sequence.

## **Basic For-In Loop**

```swift
let myArray = ["Alpha", "Beta", "Gamma", "Delta", "Epsilon"]

for item in myArray {
    print(item)
}
```

### **Using For-In Loop with Conditions**

```swift
var secondArray: [String] = []

for item in myArray {
    if item == "Gamma" {
        secondArray.append(item)
    }
}

print(secondArray)  // Prints ["Gamma"]
```

### **Iterating Over Custom Data Models**

```swift
struct LessonModel {
    let title: String
    let isFavorite: Bool
}

let allLessons = [
    LessonModel(title: "Lesson 1", isFavorite: true),
    LessonModel(title: "Lesson 2", isFavorite: false),
    LessonModel(title: "Lesson 3", isFavorite: false),
    LessonModel(title: "Lesson 4", isFavorite: true),
]

var favoriteLessons: [LessonModel] = []

for lesson in allLessons {
    if lesson.isFavorite {
        favoriteLessons.append(lesson)
    }
}

print(favoriteLessons)  // Prints only the lessons marked as favorite
```

### **Using enumerated() to Get Index and Value**

```swift
for (index, lesson) in allLessons.enumerated() {
    if index == 1 {
        continue  // Skips the rest of the loop iteration for index 1
    }
    
    print("index: \(index) || lesson: \(lesson)")
}
```

## Exercise Time 🚀

### Exercise 1: **Basic Array Iteration**

1. Create an array of integers from 1 to 10.
2. PrinPrint each integer using a for-in loop.t the count of the array.

```swift
let numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

for number in numbers {
    print(number)
}
```

### Exercise 2: **Conditional Array Iteration**

1. Create an array of strings with at least 5 different elements.
2. Use a for-in loop to create a new array containing only the elements that start with the letter “A”.

```swift
let words = ["Apple", "Banana", "Apricot", "Blueberry", "Avocado"]
var aWords: [String] = []

for word in words {
    if word.hasPrefix("A") {
        aWords.append(word)
    }
}

print(aWords)  // Prints ["Apple", "Apricot", "Avocado"]
```

### Exercise 3: **Iterating Over Custom Structs**

1. Define a struct Book with properties title and isRead.
2. Create an array of Book instances.
3. Use a for-in loop to create a new array containing only the books that have been read.

```swift
struct Book {
    let title: String
    let isRead: Bool
}

let books = [
    Book(title: "1984", isRead: true),
    Book(title: "To Kill a Mockingbird", isRead: false),
    Book(title: "The Great Gatsby", isRead: true),
    Book(title: "Moby Dick", isRead: false)
]

var readBooks: [Book] = []

for book in books {
    if book.isRead {
        readBooks.append(book)
    }
}

print(readBooks)
```

### Exercise 4: **Using enumerated()**

1. Create an array of strings.
2. Use enumerated() in a for-in loop to print each index and the corresponding value.
3. Skip the loop iteration when the index is 2.

```swift
let colors = ["Red", "Green", "Blue", "Yellow", "Purple"]

for (index, color) in colors.enumerated() {
    if index == 2 {
        continue  // Skip index 2
    }
    print("index: \(index), color: \(color)")
}
```
