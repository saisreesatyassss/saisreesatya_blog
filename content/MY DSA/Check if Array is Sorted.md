---
title: Check if Array is Sorted  
tags:  
  - Check if Array is Sorted

---

# Sorted Array Checker in Java

## Code

```java
import java.util.*;

public class SortedArray {
    
    public static boolean SortedArray(int  [ ] arr){

        for(int i=1;i<arr.length;i++){
           if( arr[i]>arr[i-1]){

           }
           else return false;
        }

        return true;
    }
    public static void  main (String [] arg){

        Scanner sc = new Scanner(System.in);

        
        int [ ] ar={1,2,3,4,5};
        

       if( SortedArray(ar)){
        System.out.println("true");
       }else {System.out.println("false");}

    }
}

```
## Overview

This Java program checks whether an array is sorted in ascending order. It traverses the array and compares each element with its previous one to determine if the array is sorted. 

## Functionality

### Input:
- The program checks a predefined array of integers.

### Output:
- It prints `true` if the array is sorted in ascending order.
- It prints `false` if the array is not sorted.

## Methods

### 1. `SortedArray(int[] arr)`
This method checks if the array is sorted by iterating through it.

**Steps**:
- The method starts from the second element (index `1`) and compares it with the previous element.
- If at any point, the current element is less than or equal to the previous one, the method returns `false` indicating the array is not sorted.
- If the loop completes without returning `false`, the method returns `true` indicating the array is sorted.

**Time Complexity**: 
- Iterating through the array has a **time complexity of O(n)**, where `n` is the number of elements.

### Main Method
- The program defines an array of integers to check.
- It calls the `SortedArray` method to check if the array is sorted.
- Depending on the result, it prints `true` or `false`.

## Example Run:

```
Array: [1, 2, 3, 4, 5]
true
```

## Time Complexity:

| Method                   | Time Complexity   |
|--------------------------|-------------------|
| `SortedArray()`           | O(n)              |

## Conclusion
- This program provides a simple and efficient method to check whether an array is sorted.
- With a time complexity of **O(n)**, the solution is optimal for checking sorting in a single pass through the array.