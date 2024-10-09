# Algorithm Time and Space Complexity Guide
<img src = 'https://d2o2utebsixu4k.cloudfront.net/media/images/09791cfc-ef2a-447e-b2f0-aa3ceea38989.jpg' width='100%'/>

**Big O Notation** is a way to express the worst-case time and space complexity of an algorithm. This guide breaks down the most common types of time complexities.

## 1. Constant Time Complexity O(1)
O(1) is known as constant complexity. This implies that the amount of time or memory does not scale with n. For time complexity, this means that n is not iterated on or recursed. Generally, a value will be selected and returned, or a value will be operated on and returned. For E.g.
```javascript
for (let i = 0; i < 10; i++) {
   // Constant number of operations
}
```
## 2. Linear Time Complexity O(n)
O(n), or linear complexity, is perhaps the most straightforward complexity to understand. O(n) means that the time/space scales 1:1 with changes to the size of n. If a new operation or iteration is needed every time n increases by one, then the algorithm will run in O(n) time.
```javascript
for (let i = 0; i < array.length; i++) {
   // Operations proportional to n
}
```
## 3. Logarithmic Time Complexity O(log n)
Often seen in divide-and-conquer algorithms, where the problem size is halved at each step. There are several common algorithms that are O(logn) a vast majority of the time, including: binary search, searching for a term in a binary search tree and adding items to a heap.
```javascript
function binarySearch(array, item) {
   let left = 0, right = array.length;
   while (left < right) {
      let mid = Math.floor((left + right) / 2);
      if (array[mid] === item) return true;
      else if (array[mid] < item) left = mid + 1;
      else right = mid - 1;
   }
   return -1;
}
```

## 4. Quadratic Time Complexity O(n^2)
Time complexity increases quadratically with input size. In short a function or an algorithm having nested loops are comes under Quadratic Time Complexity. 
```javascript
function quadraticSearch(array, item) {
   for (let i = 0; i < array.length; i++) {
      for (let j = 0; j < array.length; j++) {
         // Nested loops
      }
   }
}
```

## 5. Log-linear Time Complexity O(n log n)  
Algorithms like mergesort and quicksort often have this complexity. It combines linear and logarithmic time. This algorithm means that the (log n) operations are occurring n times. O(n log n) is commonly used in recursive sorting algorithms like binary tree sorting algorithms. 
```javascript
function mergeSort(array) {
    if (array.length === 1) {
        return array;
    }

    // Split Array in into right and left
    const length = array.length;
    const middle = Math.floor(length / 2);
    const left = array.slice(0, middle);
    const right = array.slice(middle);

    return merge(mergeSort(left), mergeSort(right));
}

function merge(left, right) {
    const result = [];
    let leftIndex = 0;
    let rightIndex = 0;

    while (leftIndex < left.length && rightIndex < right.length) {
        if (left[leftIndex] < right[rightIndex]) {
            result.push(left[leftIndex]);
            leftIndex++;
        } else {
            result.push(right[rightIndex]);
            rightIndex++;
        }
    }

    return result.concat(left.slice(leftIndex)).concat(right.slice(rightIndex));
}

const answer = mergeSort(numbers);
console.log(answer);
```

## 6. Exponential Time Complexity O(2^n) 
The number of operations doubles with each additional input. Exponential time is extremely inefficient and should be avoided unless absolutely necessary. Often O(X^n) results from having a recursive algorithm that calls X number of algorithms with n-1. The best example is Fibonacci Series. 
```javascript
function fibonacciRecursive(n) {
    if (n <= 1) {
        return n;
    }
    return fibonacciRecursive(n - 1) + fibonacciRecursive(n - 2);
}
```
## 7. Factorial Time Complexity O(n!)
This is seen in algorithms that generate all permutations of a set, where the number of possibilities grows factorially. In short O(n!), or factorial complexity, is the “worst” standard complexity that exists.
<br/>
<br/>
<img src = 'https://blog.mbedded.ninja/_astro/big-o-notation-algorithm-complexity-non-weighted.a8e4MfbB_Z13hXE8.webp' width='100%'/>
<footer> <p>Understanding the time and space complexity of algorithms helps in writing efficient code and making informed decisions during software development.</p></footer>
