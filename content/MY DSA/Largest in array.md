---
title: Largest in array
tags:
    - Largest in array
---

 
## Code

```java
import java.util.Arrays;
import java.util.Scanner;

public class Largest {

    public static void printArray(int[] arr) {
        for (int i = 0; i < arr.length; i++) {
            System.out.print(arr[i] + " "); 
        }
        System.out.println();  
    }

    public static int findAndPrintLargestUsingSort(int[] arr) {
        Arrays.sort(arr); 
        int largest = arr[arr.length - 1];  
        return largest;
    }

    public static int findAndPrintLargestUsingArray(int[] arr) {
        int largest = arr[0];  
        for (int i = 1; i < arr.length; i++) {  
            if (arr[i] > largest) {
                largest = arr[i]; 
            }
        }
        return largest;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter the number of elements: ");
        int n = sc.nextInt();
        int[] arr = new int[n];

        System.out.println("Enter " + n + " elements:");
        for (int i = 0; i < n; i++) {
            arr[i] = sc.nextInt();
        }

        printArray(arr);

        System.out.println("Largest element using sorting: " + findAndPrintLargestUsingSort(arr));

        System.out.println("Largest element using linear search: " + findAndPrintLargestUsingArray(arr));

        sc.close(); 
    }
}
```
 

# Largest Element Finder in Java

## Overview

This Java program finds the largest element from an array using two different approaches:
1. **Using sorting**: The array is sorted, and the last element (the largest) is returned.
2. **Using a linear search**: The array is traversed to find the largest element without sorting.

## Functionality

### Input:
- The program takes the number of elements (`n`) and the `n` integers as input from the user.

### Output:
- The program displays the array entered by the user.
- It then prints the largest element of the array using:
  1. Sorting
  2. A simple linear search

## Methods

### 1. `printArray(int[] arr)`
This method prints the elements of the array.

**Parameters**: `int[] arr` - the array to be printed.

### 2. `findAndPrintLargestUsingSort(int[] arr)`
This method sorts the array and returns the largest element, which is the last element of the sorted array.

**Steps**:
- Sorts the array using `Arrays.sort()`.
- Returns the last element.

**Time Complexity**: 
- Sorting an array using the `Arrays.sort()` method has a **time complexity of O(n log n)** where `n` is the number of elements in the array.

### 3. `findAndPrintLargestUsingArray(int[] arr)`
This method finds the largest element by iterating through the array, comparing each element to track the largest one.

**Steps**:
- Initialize the largest element as the first element.
- Loop through the array to compare each element with the largest one and update the largest if a larger element is found.

**Time Complexity**: 
- Iterating through the array has a **time complexity of O(n)**, where `n` is the number of elements.

### Main Method
- Takes input from the user for the number of elements and the elements of the array.
- Calls the `printArray` method to display the array.
- Calls both `findAndPrintLargestUsingSort` and `findAndPrintLargestUsingArray` methods to display the largest element found through each approach.

## Example Run:

```
Enter the number of elements: 5
Enter 5 elements:
23 1 45 67 12
23 1 45 67 12 
Largest element using sorting: 67
Largest element using linear search: 67
```

## Time Complexity:

| Method                                  | Time Complexity   |
|-----------------------------------------|-------------------|
| `findAndPrintLargestUsingSort()`         | O(n log n)        |
| `findAndPrintLargestUsingArray()`        | O(n)              |

## Conclusion
- **Sorting** is useful when you need additional operations that require ordering, but it is less efficient for simply finding the largest element due to the O(n log n) complexity.
- **Linear search** is more efficient for this specific task, with a time complexity of O(n).

This program demonstrates two common ways of approaching the problem of finding the largest element, and it highlights the differences in time complexity between them.
