## **Operators and Conditions** 📖

Hi, welcome to swift basics, the topics we will cover here are arithmetic operators, comparison operators and conditions.

## Usage 🔨

### Arithmetic Operators

For 4 operations in mathematics

| Plus | Minus | Multiply | Division |
| --- | --- | --- | --- |
| + | - | * | / |

### Create Variables

```swift
var likeCount: Double = 5
var commentCount: Double = 0
var viewCount: Double = 100

likeCount = 5 + 1
```

### Plus

```swift
likeCount = likeCount + 1
likeCount += 1
```

### Minus

```swift
likeCount = likeCount - 1
likeCount -= 1
```

### Multiplication

```swift
likeCount = likeCount * 1.5
likeCount *= 1.5
```

### Division

```swift
likeCount = likeCount / 2
likeCount /= 2
```

### PEMDAS - Order of operations does matter!

```swift
likeCount = likeCount - 1 * 1.5
likeCount = (likeCount - 1) * 1.5
```

### Comparison Operators

They are used too much and compare two values.

| Equal | Not Equal | Bigger | Less | Bigger or Equal | Less or Equal |
| --- | --- | --- | --- | --- | --- |
| == | != | < | > | <= | >= |

```swift
if likeCount == 5 {
    print("Post has 5 likes.")
} else {
    print("Post does NOT have 5 likes.")
}

if likeCount != 5 {
    print("Post does NOT have 5 likes.")
}

if likeCount > 5 {
    print("Post has greater than 5 likes.")
}

if likeCount >= 5 {
    print("Post has greater than or equal to 5 likes.")
}

if likeCount < 5 {
    print("Post has less than 5 likes.")
}

if likeCount <= 5 {
    print("Post has less than or equal to 5 likes.")
}
```

### Conditions

Conditions are of great importance in the software world. It allows you to control the flow of the code you program.

```swift
let score = 9

if score > 20 {
    print("The weather is sunny and hot")
}else if score >= 10 {
    print("The weather is cloudy and warm")
}else{
    print("The weather is rainy or snowy and cold")
}

```

### Combining conditions

| And | Or |
| --- | --- |
| && - Works If Both Statements are True | ll - Even a Statement Works if True |

```swift
// Uses the conditions together
let age1 = 21
let age2 = 17

if age1 > 18 && age2 > 18 {
    print("You can both get a driver's license.")
}else if age1 > 18 || age2 > 18 {
    print("Only one of you can get a driver's license.")
}else{
    print("You both can't get a driver's license.")
}
// Only one of you can get a driver's license.

```

### The Ternary Operator

```swift
// Is the same as if else. Makes it harder to read but is written shorter.
let num1 = 10
let num2 = 15

var result = num1>num2 ? "First num bigger than second" : "Second num bigger than first"
print(result) // Second num bigger than first

```

### Switch Statements

```swift
// Used to control the flow of certain expressions.
let myState = "Happy"

switch myState {
case "Happy":
    print("You are look so happy!!")
case "Sad":
    print("Are you okay?")
case "Bored":
    print("Come, Let go to cinema!")
    fallthrough
default:
    print("I don't know how about your feels.")
}
// You are look so happy!!

```

### Range operators

```swift
// It is used to specify a range.
let result = 5

switch result {
case 0..<2:
    print("Bad result")
case 3..<7:
    print("Okay, but not good.")
default:
    print("Perfect!")
}
// Okay, but not good.

```

## Exercise Time 🚀

### Exercise 1: **Arithmetic Operators**

1. **Addition:**
    
    ```swift
    var myDouble: Double = 10.0
    myDouble = myDouble + 5.5
    print(myDouble) // 15.5
    ```
    
2. **Subtraction:**
    
    ```swift
    var myDouble: Double = 20.0
    myDouble = myDouble - 4.5
    print(myDouble) // 15.5
    ```
    
3. **Multiplication:**
    
    ```swift
    var myDouble: Double = 3.0
    myDouble = myDouble * 2.5
    print(myDouble) // 7.5
    ```
    
4. **Division:**
    
    ```swift
    var myDouble: Double = 9.0
    myDouble = myDouble / 3.0
    print(myDouble) // 3.0
    ```
    

### Exercise 2: **Comparison Operators**

1. **Equality:**
    
    ```swift
    let a: Int = 10
    let b: Int = 20
    if a == b {
        print("a and b are equal")
    } else {
        print("a and b are not equal")
    }
    // a and b are not equal
    ```
    
2. **Inequality:**
    
    ```swift
    let a: Int = 15
    let b: Int = 15
    if a != b {
        print("a and b are not equal")
    } else {
        print("a and b are equal")
    }
    // a and b are equal
    ```
    
3. **Greater than:**
    
    ```swift
    let myDouble: Double = 4.5
    if myDouble > 3.0 {
        print("myDouble is greater than 3.0")
    } else {
        print("myDouble is not greater than 3.0")
    }
    // myDouble is greater than 3.0
    ```
    
4. **Less than or equal to:**
    
    ```swift
    let myDouble: Double = 2.5
    if myDouble <= 2.5 {
        print("myDouble is less than or equal to 2.5")
    } else {
        print("myDouble is greater than 2.5")
    }
    // myDouble is less than or equal to 2.5
    ```
    

### Exercise 3: **Conditions**

1. **Basic Condition:**
    
    ```swift
    let number: Int = 25
    if number > 20 {
        print("Büyük")
    } else {
        print("Küçük veya Eşit")
    }
    ```
    
2. **Nested Condition:**
    
    ```swift
    let number: Int = 15
    if number > 10 && number < 20 {
        print("Orta")
    } else {
        print("Dışında")
    }
    ```
    
3. **Else If Condition:**
    
    ```swift
    let score: Int = 50
    if score > 80 {
        print("80'den büyük")
    } else if score > 60 {
        print("60'tan büyük")
    } else {
        print("60'tan küçük")
    }
    ```
    

### Exercise 4: **Combining Conditions**

1. **Using And (&&) Operator:**
    
    ```swift
    let age1: Int = 25
    let age2: Int = 30
    if age1 > 20 && age2 > 20 {
        print("İkisi de büyük")
    } else {
        print("Biri veya ikisi küçük")
    }
    ```
    
2. **Using Or (||) Operator:**
    
    ```swift
    let age1: Int = 18
    let age2: Int = 22
    if age1 > 20 || age2 > 20 {
        print("Birisi büyük")
    } else {
        print("İkisi de küçük")
    }
    ```
    

### Exercise 5: **Ternary Operator**

1. **Basic Usage:**
    
    ```swift
    let num1: Int = 7
    let num2: Int = 10
    let result = num1 > num2 ? "Büyük sayı: \(num1)" : "Büyük sayı: \(num2)"
    print(result) // Büyük sayı: 10
    ```
    

### Exercise 6: **Switch Statements**

1. **Basic Switch Statements:**
    
    ```swift
    let mood: String = "Sad"
    switch mood {
    case "Happy":
        print("You are happy!")
    case "Sad":
        print("You are sad.")
    case "Angry":
        print("You are angry!")
    default:
        print("Mood is unknown.")
    }
    // You are sad.
    ```
    

### Exercise 7: **Range Operators**

1. **Basic Range:**
    
    ```swift
    let score: Int = 4
    switch score {
    case 0..<3:
        print("Low score")
    case 3..<7:
        print("Average score")
    default:
        print("High score")
    }
    // Average score
    ```
