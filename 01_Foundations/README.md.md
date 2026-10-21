
# 01 - Foundations: JavaScript DSA

## 1. Find Frequency of Each Element

### Problem
Given an array of numbers, count how many times each element appears and return the frequency of each element.

### Example Test Cases

**Test Case 1**
- Input: `[1, 2, 2, 3, 1, 1]`
- Output: `{ 1: 3, 2: 2, 3: 1 }`

**Test Case 2**
- Input: `[5, 5, 5]`
- Output: `{ 5: 3 }`

**Test Case 3**
- Input: `[]`
- Output: `{}`

### Complexities

**Time Complexity: O(n)**

We iterate through the array once. If the array contains n elements, we process each element once.

**Space Complexity: O(k)**

We store the frequency of each distinct element in an object. If there are k distinct elements, we need space for k entries. In the worst case, k = n, so the space complexity becomes O(n).

---

## 2. Count Character Occurrences

### Problem
Given a string, count how many times each character occurs.

### Example Test Cases

**Test Case 1**
- Input: `"banana"`
- Output: `{ b: 1, a: 3, n: 2 }`

**Test Case 2**
- Input: `"hello"`
- Output: `{ h: 1, e: 1, l: 2, o: 1 }`

**Test Case 3**
- Input: `"aaa"`
- Output: `{ a: 3 }`

**Test Case 4**
- Input: `""`
- Output: `{}`

### Complexities

**Time Complexity: O(n)**

We visit every character in the string once. If the string contains n characters, the total work grows linearly with n.

**Space Complexity: O(k)**

We store one entry for each distinct character, where k is the number of distinct characters. For a fixed character set, this can be considered O(1) space; otherwise, it is O(k).

---

## 3. Remove Duplicates Using Set

### Problem
Given an array, return a new array containing only unique elements. Preserve the original order of their first occurrence.

### Example Test Cases

**Test Case 1**
- Input: `[1, 2, 2, 3, 1, 4]`
- Output: `[1, 2, 3, 4]`

**Test Case 2**
- Input: `["a", "b", "a", "c"]`
- Output: `["a", "b", "c"]`

**Test Case 3**
- Input: `[1, 2, 3]`
- Output: `[1, 2, 3]`

**Test Case 4**
- Input: `[]`
- Output: `[]`

### Complexities

**Time Complexity: O(n) average**

We process each array element and insert it into a Set. Set operations have average sublinear or constant-time behavior in typical implementations; for standard interview analysis, this approach is commonly treated as O(n) overall.

**Space Complexity: O(n)**

In the worst case, every element is unique, so the Set and resulting array store up to n elements.

---

## 4. Count Word Frequencies Using Map

### Problem
Given a sentence, count how many times each word appears using a Map.

Treat words with different capitalization as the same word.

### Example Test Cases

**Test Case 1**
- Input: `"apple banana apple orange banana apple"`
- Output: `Map { "apple" => 3, "banana" => 2, "orange" => 1 }`

**Test Case 2**
- Input: `"Hello hello HELLO"`
- Output: `Map { "hello" => 3 }`

**Test Case 3**
- Input: `"cat dog cat"`
- Output: `Map { "cat" => 2, "dog" => 1 }`

**Test Case 4**
- Input: `""`
- Output: An empty Map

### Complexities

**Time Complexity: O(n)**

Assuming n is the total number of characters in the sentence, splitting the sentence, normalizing the words, and counting them takes O(n) overall under typical assumptions.

**Space Complexity: O(n)**

In the worst case, all words are distinct. The Map and the word collection can require space proportional to the input size.

---

## 5. Create a Frequency Counter Using an Object

### Problem
Write a reusable function that accepts an array and returns an object containing the frequency of each element.

### Example Test Cases

**Test Case 1**
- Input: `["red", "blue", "red", "green", "blue", "red"]`
- Output: `{ red: 3, blue: 2, green: 1 }`

**Test Case 2**
- Input: `["apple", "apple", "apple"]`
- Output: `{ apple: 3 }`

**Test Case 3**
- Input: `["cat", "dog", "bird"]`
- Output: `{ cat: 1, dog: 1, bird: 1 }`

**Test Case 4**
- Input: `[]`
- Output: `{}`

### Complexities

**Time Complexity: O(n) average**

We iterate through the array once and update an object's property for each element. Object property access and updates are typically treated as O(1) average time.

**Space Complexity: O(k)**

The object stores k distinct elements. In the worst case, every element is unique, giving O(n) space complexity.

---

## 6. Find Complexity of a Single Loop

### Problem
Determine the time and space complexity of a loop that visits every element in an array.

### Example Test Cases

**Test Case 1**
```javascript
function printElements(arr) {
    for (let i = 0; i < arr.length; i++) {
        console.log(arr[i]);
    }
}
```
- Input: `[10, 20, 30]`
- Output: `10 20 30`
- Iterations: `3`

**Test Case 2**
- Input: An array of 100 elements
- Iterations: `100`

**Test Case 3**
- Input: An empty array
- Iterations: `0`

### Complexities

**Time Complexity: O(n)**

The loop runs n times for an array of n elements. If the input size doubles, the number of iterations approximately doubles.

**Auxiliary Space Complexity: O(1)**

The loop uses only a fixed amount of extra memory for the loop counter and other variables, regardless of the input size. This excludes the input array itself.

---

## 7. Find Complexity of Nested Loops

### Problem
Determine the time and space complexity of two nested loops, where both loops iterate over the entire array.

### Example Test Cases

**Test Case 1**
```javascript
function printPairs(arr) {
    for (let i = 0; i < arr.length; i++) {
        for (let j = 0; j < arr.length; j++) {
            console.log(arr[i], arr[j]);
        }
    }
}
```
- Input: `[1, 2, 3]`
- Output: All possible ordered pairs
- Total iterations: `3 × 3 = 9`

**Test Case 2**
- Input size: `5`
- Total iterations: `5 × 5 = 25`

**Test Case 3**
- Input size: `10`
- Total iterations: `10 × 10 = 100`

### Complexities

**Time Complexity: O(n²)**

The outer loop executes n times. For each outer iteration, the inner loop also executes n times. Therefore, total iterations equal n × n = n².

**Auxiliary Space Complexity: O(1)**

Only the two loop counters and a fixed amount of extra memory are used. The number of iterations increases, but the extra memory remains constant.

---

## 8. Analyze a Loop That Doubles Its Counter

### Problem
Determine the time and space complexity of a loop in which the counter doubles after every iteration.

### Example Test Cases

**Test Case 1**
```javascript
function doublingLoop(n) {
    for (let i = 1; i < n; i *= 2) {
        console.log(i);
    }
}
```
- Input: `n = 20`
- Values of `i`: `1, 2, 4, 8, 16`
- Total iterations: `5`

**Test Case 2**
- Input: `n = 8`
- Values of `i`: `1, 2, 4`
- Total iterations: `3`

**Test Case 3**
- Input: `n = 1`
- Total iterations: `0`

### Complexities

**Time Complexity: O(log n)**

The counter doubles on each iteration. After k iterations, its value is approximately 2^k. The loop stops when 2^k reaches n, so k is approximately log₂(n).

Therefore, the number of iterations grows logarithmically rather than linearly.

**Auxiliary Space Complexity: O(1)**

Only the loop counter and a fixed amount of extra memory are used.

---

## 9. Compare Two Solutions With Different Complexities

### Problem
Given an array and a target value, determine whether the target exists in the array. Compare linear search with a Set-based approach.

### Example Test Cases

**Test Case 1**
- Input: `arr = [10, 20, 30, 40], target = 30`
- Linear search output: `true`
- Set-based output: `true`

**Test Case 2**
- Input: `arr = [10, 20, 30], target = 50`
- Linear search output: `false`
- Set-based output: `false`

**Test Case 3**
- Input: `arr = [], target = 10`
- Linear search output: `false`
- Set-based output: `false`

### Complexities

**Approach 1: Linear Search**

- Time Complexity: O(n) worst case.
- Auxiliary Space Complexity: O(1).

We check elements one by one. In the worst case, the target is absent or appears at the end, so all n elements are examined.

**Approach 2: Set-Based Search**

- Building the Set: O(n) average time.
- Looking up one target after building: O(1) average time.
- Total time for building and one lookup: O(n) average.
- Auxiliary Space Complexity: O(n).

We store the elements in a Set, which uses additional memory. Once constructed, it supports average constant-time membership checks.

**Which approach is better?**

For one lookup, linear search is often simpler and avoids building a Set. For repeated lookups in the same array, building a Set once can be more efficient overall.

---

## 10. Analyze Array Operation Complexities

### Problem
Determine the time complexity of common JavaScript array operations and explain why their costs differ.

### Example Test Cases

**Test Case 1: Access an Element**
```javascript
const arr = [10, 20, 30, 40];
console.log(arr[2]);
```
- Output: `30`
- Time Complexity: O(1)

**Test Case 2: Search for an Element**
```javascript
const arr = [10, 20, 30, 40];
console.log(arr.includes(40));
```
- Output: `true`
- Worst-case Time Complexity: O(n)

**Test Case 3: Add an Element at the End**
```javascript
const arr = [10, 20, 30];
arr.push(40);
```
- Output: `[10, 20, 30, 40]`
- Amortized Time Complexity: O(1)

**Test Case 4: Add an Element at the Beginning**
```javascript
const arr = [10, 20, 30];
arr.unshift(5);
```
- Output: `[5, 10, 20, 30]`
- Time Complexity: O(n)

### Complexities

| Array Operation | Time Complexity | Explanation |
|---|---|---|
| Access by index | O(1) | Directly accesses the requested index. |
| Update by index | O(1) | Updates a value at a known index. |
| `includes()` | O(n) | May examine every element. |
| `indexOf()` | O(n) | Searches elements sequentially. |
| `push()` | O(1) amortized | Adds to the end; occasional resizing may take O(n). |
| `pop()` | O(1) | Removes the last element. |
| `unshift()` | O(n) | Existing elements generally need to shift. |
| `shift()` | O(n) | Remaining elements generally need to shift. |
| `slice()` | O(n) | Copies the selected elements. |
| `forEach()` | O(n) | Visits every element. |
| `sort()` | O(n log n) typical | Typical comparison-sort performance; exact complexity depends on the JavaScript engine and input. |

**Auxiliary Space Complexity**

Array operations that only access, update, or iterate over existing elements typically use O(1) auxiliary space if the callback uses no additional growing storage.

Operations such as `slice()` create a new array and generally require O(n) additional space in the worst case. Sorting may use additional implementation-dependent memory.

### Key Questions to Revise
- Why are `push()` and `pop()` usually efficient?
- Why are `shift()` and `unshift()` generally O(n)?
- What is the difference between average-case and worst-case complexity?
- What is the difference between total space and auxiliary space?
