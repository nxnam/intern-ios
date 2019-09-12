# The Basics

## Khai báo biến

```javascript
let maximumNumberOfLoginAttempts = 10
var currentLoginAttempt: Int
```
var : Có thể thay đổi giá trị\
let : Không thể thay đổi giá trị

Swift tự suy luận kiểu của giá trị khi khai báo

# Strings and Characters
## Khai báo

#### Chuỗi có giá trị ban đầu:

```javascript
let someString = "Some string literal value"
```
#### Chuỗi rỗng

```javascript
var emptyString = ""                 
var anotherEmptyString = String()
```

## Nội dung trong ba dấu nháy kép
```javascript
let multilineString = """
These are the same.
"""
```

Nó sẽ in ra màn hình đúng như những gì ta nhập vào kể cả khoảng trắng. Nếu muốn viết kí tự đặc biệt thì đặt sau dấu \

## Kiểm tra chuỗi đó có rỗng

```javascript
var variableString = "Horse"
variableString += " and carriage"
```

## String có thể tao ra từ một mảng Characters

```javascript
let catCharacters: [Character] = ["C", "a", "t", "!", "🐱"]
let catString = String(catCharacters)
print(catString)
// Prints "Cat!🐱"
```

## Nối chuỗi

```javascript
let string1 = "hello"
let string2 = " there"
var welcome = string1 + string2
// welcome now equals "hello there"

var instruction = "look over"
instruction += string2
// instruction now equals "look over there"
```

## Đếm số lượng Character trong String bằng thuộc tính .count

```javascript
let unusualMenagerie = "Koala 🐨, Snail 🐌, Penguin 🐧, Dromedary 🐪"
print("unusualMenagerie has \(unusualMenagerie.count) characters")
// Prints "unusualMenagerie has 40 characters"
```

## Chỉ số chuỗi
```javascript
let greeting = "Guten Tag!"
greeting[greeting.startIndex]
// G
greeting[greeting.index(before: greeting.endIndex)]
// !
greeting[greeting.index(after: greeting.startIndex)]
// u
let index = greeting.index(greeting.startIndex, offsetBy: 7)
greeting[index]
// a
```
Thuộc tính endIndex trỏ đến sau vị trí sau phần tử cuối cùng của String

Thuộc tính .indices dùng để lấy chỉ mục. Nếu for bình thường nó sẽ lấy giá trị

Không thể truyền trực tiếp số nguyên vào ví dụ greeting[1] để lấy giá trị 'u'

```javascript
for index in greeting.indices {
    print("\(greeting[index]) ", terminator: "")
}
// Prints "G u t e n   T a g ! "
```

## Chèn và xoá

```javascript
var welcome = "hello"
welcome.insert("!", at: welcome.endIndex)
// welcome now equals "hello!"

welcome.insert(contentsOf: " there", at: welcome.index(before: welcome.endIndex))
// welcome now equals "hello there!"

welcome.remove(at: welcome.index(before: welcome.endIndex))
// welcome now equals "hello there"

let range = welcome.index(welcome.endIndex, offsetBy: -6)..<welcome.endIndex
welcome.removeSubrange(range)
// welcome now equals "hello"
```

## Kiểm tra tiền tố và hậu tố sửu dụng thuộc tính hasPrefix("Trước") và hasSuffix("Sau")

# Collection Types

### Khai báo

```javascript
var names = ["Mic", "Sam", "Christine"]
var names = ["Mic" : 1, "Sam" : 2, "Christine" : 3]
var favoriteGenres: Set = ["Rock", "Classical", "Hip hop"]

var names: [String] = []
var lookup: [String: Int] = [:]
var letters = Set<Character>()
```

Các thuộc tính truy cập sửa xoá khá quen thuộc với những ngôn ngữ lập trình cơ bản

Các phần tử trong Set không lặp lại

Set có một số thuộc tính xem trong docs swift nếu cần [Bấm vào Đây](https://docs.swift.org/swift-book/LanguageGuide/CollectionTypes.html#ID490)

# Control Flow

## For-In Loops

```javascript
let names = ["Anna", "Alex", "Brian", "Jack"]
for name in names {
    print("Hello, \(name)!")
}
// Hello, Anna!
// Hello, Alex!
// Hello, Brian!
// Hello, Jack!
```
#### Chạy từ 1 đến 5
```javascript
for index in 1...5 {
    print("\(index) times 5 is \(index * 5)")
}
```
#### chạy từ 0 đến n - 1
```javascript
let names = ["Anna", "Alex", "Brian", "Jack"]
let count = names.count
for i in 0..<count {
    print("Person \(i + 1) is called \(names[i])")
}
// Person 1 is called Anna
// Person 2 is called Alex
// Person 3 is called Brian
// Person 4 is called Jack
```

#### Tương tự ta có

```javascript
for name in names[2...] {
    print(name)
}
// Brian
// Jack

for name in names[..<2] {
    print(name)
}
// Anna
// Alex
```
