## AccessControl 📖

Hi, welcome to swift basics, the topics we will cover here are access control. In Swift, access levels are crucial for ensuring code security and encapsulation. Access levels determine how classes, structures, and other code entities can be accessed from different parts of the code. By using access levels correctly, you can make your code more secure, readable, and maintainable.

## **Access Levels**

- **open**: The most permissive access level. Code outside the module can subclass and override methods of an open class.
- **public**: Code outside the module can access and use a public class or structure but cannot subclass it.
- **internal**: The default access level. Accessible within the entire module but not outside of it.
- **fileprivate**: Accessible only within the same file.
- **private**: The most restrictive access level. Accessible only within the same declaration scope.

## **Example Code**

```swift
import Foundation

// Rule of thumb:
// We want everything to be as private as possible!
// This makes your code easier to read/debug and is good coding practice!

struct MovieModel {
    let title: String
    let genre: MovieGenre
    private(set) var isFavorite: Bool
    
    func updateFavoriteStatus(newValue: Bool) -> MovieModel {
        MovieModel(title: title, genre: genre, isFavorite: newValue)
    }
    
    mutating func updateFavoriteStatus2(newValue: Bool) {
        isFavorite = newValue
    }
}

enum MovieGenre {
    case comedy, action, horror
}

class MovieManager {
    // public
    public var movie1 = MovieModel(title: "Avatar", genre: .action, isFavorite: false)
    
    // private
    private var movie2 = MovieModel(title: "Step Brothers", genre: .comedy, isFavorite: false)
    
    // read is public, set is private
    private(set) var movie3 = MovieModel(title: "Avenger", genre: .action, isFavorite: false)
    
    func updateMovie3(isFavorite: Bool) {
        movie3.updateFavoriteStatus2(newValue: isFavorite)
    }
}

let manager = MovieManager()

let someValue = manager.movie3

// Version 1
// We can GET and SET the value from outside the object.
// "too public"
let movie1 = manager.movie1
manager.movie1 = manager.movie1.updateFavoriteStatus(newValue: true)

// Version 2
// We can't GET or SET the value from outside the object.
// "cannot access"
// let movie2 = manager.movie2
// manager.movie2 = manager.movie2.updateFavoriteStatus(newValue: true)

// Version 3
// We can GET the value from outside the object, but we can't SET the value from outside the object.
// "best practice"
let movie3 = manager.movie3
// manager.movie3 = manager.movie3.updateFavoriteStatus(newValue: true)
manager.updateMovie3(isFavorite: true)

// Note: private & public are by far the most common but there are many others
//
// open
// public
// internal
// fileprivate
// private
```

## Exercise Time 🚀

### Exercise 1: **Create a new structure: BookModel**

1. It should have the following properties:
    
    •	title: String
    •	author: String
    •	isBestSeller: Bool (with private set access level)
    
2. Add a method updateBestSellerStatus(newValue: Bool) to update the isBestSeller status.
3. Ensure that the properties are appropriately encapsulated using access levels.

```swift
struct BookModel {
    let title: String
    let author: String
    private(set) var isBestSeller: Bool
    
    mutating func updateBestSellerStatus(newValue: Bool) {
        isBestSeller = newValue
    }
}
```

### Exercise 2: **Create a class: LibraryManager**

1. It should have a public property book1 of type BookModel.
2. It should have a private property book2 of type BookModel.
3. It should have a private(set) property book3 of type BookModel.
4. Add a method updateBook3BestSellerStatus(newValue: Bool) to update the isBestSeller status of book3.

```swift
class LibraryManager {
    public var book1 = BookModel(title: "1984", author: "George Orwell", isBestSeller: false)
    private var book2 = BookModel(title: "To Kill a Mockingbird", author: "Harper Lee", isBestSeller: false)
    private(set) var book3 = BookModel(title: "The Great Gatsby", author: "F. Scott Fitzgerald", isBestSeller: false)
    
    func updateBook3BestSellerStatus(newValue: Bool) {
        book3.updateBestSellerStatus(newValue: newValue)
    }
}

let libraryManager = LibraryManager()

// Accessing and modifying book1
let book1 = libraryManager.book1
libraryManager.book1.updateBestSellerStatus(newValue: true)

// Trying to access book2 will result in an error
// let book2 = libraryManager.book2

// Accessing book3 but modifying through method
let book3 = libraryManager.book3
libraryManager.updateBook3BestSellerStatus(newValue: true)
```

### Exercise 3: **Reflection on Access Levels**

1. Explain why using private(set) is useful in structuring your code.
2. Give an example of when you would use fileprivate instead of private.

**Answer:**

•	Using private(set) is useful because it allows other parts of the code to read a property but prevents them from modifying it. This helps maintain control over how and when the property can be changed, reducing the risk of unexpected changes and making the code easier to debug.

•	fileprivate is used when you want to restrict access to a property or method to the same file but allow access from multiple classes or structures within that file. This is useful in larger files where multiple types need to interact closely without exposing their details to other parts of the codebase. For example, if you have a helper function or property that should only be used by the classes in the same file but not by others, you would use fileprivate.
