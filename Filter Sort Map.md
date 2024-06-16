## Filtering, Sorting, and Mapping Arrays in Swift 📖

In Swift, you can perform various operations on arrays using higher-order functions like `filter`, `sorted`, and `map`. These functions allow you to create new arrays based on certain criteria or transform the elements of an array.

## Filtering Arrays

The `filter` function is used to create a new array containing only the elements that satisfy a given condition.

```swift
struct DatabaseUser {
    let name: String
    let isPremium: Bool
    let order: Int
}

var allUsers: [DatabaseUser] = [
    DatabaseUser(name: "Nick", isPremium: true, order: 4),
    DatabaseUser(name: "Emily", isPremium: false, order: 1),
    DatabaseUser(name: "Samantha", isPremium: true, order: 3),
    DatabaseUser(name: "Joe", isPremium: true, order: 10000),
    DatabaseUser(name: "Chris", isPremium: false, order: 2),
]

// Filtering users to get only premium users
var allPremiumUsers: [DatabaseUser] = allUsers.filter { user in
    user.isPremium
}

// Alternative shorthand syntax
var allPremiumUsers2: [DatabaseUser] = allUsers.filter { $0.isPremium }

print(allPremiumUsers)

```

## Sorting Arrays

The `sorted` function sorts the elements of an array based on a given condition and returns a new array.

```swift
// Sorting users based on their order property
var orderedUsers: [DatabaseUser] = allUsers.sorted { user1, user2 in
    return user1.order < user2.order
}

// Alternative shorthand syntax
var orderedUsers2: [DatabaseUser] = allUsers.sorted(by: { $0.order < $1.order })

print(orderedUsers)

```

## Mapping Arrays

The `map` function transforms each element of an array using a given closure and returns a new array containing the transformed elements.

```swift
// Mapping users to get an array of their names
var userNames: [String] = allUsers.map { user in
    return user.name
}

// Alternative shorthand syntax
var userNames2: [String] = allUsers.map { $0.name }

print(userNames)
```

## Exercise Time 🚀

### Exercise 1: Filter Exercise

1. Create an array of `DatabaseUser` instances.
2. Use the `filter` function to create a new array containing only the users whose `order` is greater than 100.

```swift
var highOrderUsers: [DatabaseUser] = allUsers.filter { $0.order > 100 }
print(highOrderUsers)
```

### Exercise 2: **Sort Exercise**

1. Create an array of `DatabaseUser` instances.
2. Use the `sorted` function to create a new array sorted by the users' names in alphabetical order.

```swift
var alphabeticallyOrderedUsers: [DatabaseUser] = allUsers.sorted { $0.name < $1.name }
print(alphabeticallyOrderedUsers)
```

### Exercise 3: **Map Exercise**

1. Create an array of `DatabaseUser` instances.
2. Use the `map` function to create a new array of strings containing the names of premium users only.

```swift
var premiumUserNames: [String] = allUsers.filter { $0.isPremium }.map { $0.name }
print(premiumUserNames)
```

### Exercise 4: **Combined Exercise**

1. Create an array of `DatabaseUser` instances.
2. First, filter the array to get only the non-premium users.
3. Then, sort the filtered array by the `order` property in descending order.
4. Finally, map the sorted array to get an array of the names of the non-premium users.

```swift
var nonPremiumOrderedUserNames: [String] = allUsers
    .filter { !$0.isPremium }
    .sorted { $0.order > $1.order }
    .map { $0.name }
print(nonPremiumOrderedUserNames)
```
