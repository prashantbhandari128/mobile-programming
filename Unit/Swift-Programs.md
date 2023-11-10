<div align="center">

[**_``Go Back``_**](../README.md)

# Some Swift Program

</div>

### (1) Swift program to find sum of all elements of 1-D array?

**Program:**

```Swift
func findSumOfArrayElements(array: [Int]) -> Int {
    var sum = 0
    for element in array {
        sum += element
    }
    return sum
}

let numbers = [10, 20, 30, 40, 50]
let sum = findSumOfArrayElements(array: numbers)
print("Sum of array elements: \(sum)")

```

Without Function:

```Swift
let numbers = [10, 20, 30, 40, 50]
var sum = 0

for element in numbers {
    sum += element
}

print("Sum of array elements: \(sum)")
```

**Output:**

```
Sum of array elements: 150
```

### (2) Swift program to find the minimum among 10 numbers using function:

**Program:**

```Swift
func findMinimumAmong(numbers: [Int]) -> Int {
    var minimum = numbers[0]
    for number in numbers {
        if number < minimum {
            minimum = number
        }
    }
    return minimum
}

let numbers = [23, 45, 12, 67, 5, 78, 34, 9, 56, 90]
let minimum = findMinimumAmong(numbers: numbers)
print("The minimum among the numbers is: \(minimum)")
```

**Output:**

```
The minimum among the numbers is: 5
```

### (3) Swift program to find Profit or Loss based on CP and SP.

**Program:**

```Swift
func calculateProfitOrLoss(costPrice: Double, sellingPrice: Double) -> String {
    if sellingPrice > costPrice {
        let profit = sellingPrice - costPrice
        return "Profit of Rs \(profit)"
    } else if sellingPrice < costPrice {
        let loss = costPrice - sellingPrice
        return "Loss of Rs \(loss)"
    } else {
        return "No Profit, No Loss"
    }
}

let costPrice = 100.0
let sellingPrice = 120.0
let result = calculateProfitOrLoss(costPrice: costPrice, sellingPrice: sellingPrice)
print(result)
```
**Output:**

```
Profit of Rs 20.0
```

### (4) Swift program to find factorial of number using function

**Program:**

```Swift
func factorial(number: Int) -> Int {
    if number == 0 {
        return 1
    } else {
        return number * factorial(number: number - 1)
    }
}

let inputNumber = 5 
if inputNumber < 0 {
    print("Factorial is undefined for negative numbers.")
} else {
    let result = factorial(number: inputNumber)
    print("Factorial of \(inputNumber) is \(result)")
}
```

**Output:**
```
Factorial of 5 is 120
```

### (5) Swift program to find the maximum among 10 numbers using function:

**Program:**

```Swift
func findMaximumAmong(numbers: [Int]) -> Int {
    var maximum = numbers[0]
    for number in numbers {
        if number > maximum {
            maximum = number
        }
    }
    return maximum
}

let numbers = [23, 45, 12, 67, 5, 78, 34, 9, 56, 90]
let maximum = findMaximumAmong(numbers: numbers)
print("The maximum among the numbers is: \(maximum)")
```

**Output:**
```
The maximum among the numbers is: 90
```

### (6) Swift program to find the sort 10 numbers:

**Program:**
```Swift
func bubbleSort(numbers: inout [Int]) {
    let n = numbers.count
    for i in 0..<n {
        for j in 0..<(n - i - 1) {
            if numbers[j] > numbers[j + 1] {
                // Swap numbers[j] and numbers[j + 1]
                let temp = numbers[j]
                numbers[j] = numbers[j + 1]
                numbers[j + 1] = temp
            }
        }
    }
}

// Example usage:
var Numbers = [9, 3, 7, 1, 6, 8, 2, 5, 10, 4]

bubbleSort(numbers: &Numbers)
print("Sorted Numbers: \(Numbers)")
```

**Output:**
```
Sorted Numbers: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```