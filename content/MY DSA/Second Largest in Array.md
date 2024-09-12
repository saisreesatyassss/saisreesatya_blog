---
title: Second Largest in Array  
tags:  
  - Second Largest in Array

---

# Second Largest Element Finder in Java


## Code Implementation

```java
import java.util.*;

public class Secondlargestinthearray {
    
    // Method to print array elements
    public static void printarr(int[] arr) {
        for (int i = 0; i < arr.length; i++) {
            System.out.print(arr[i] + " ");
        }
        System.out.println();
    }

    // Method to find the second-largest element using sorting
    public static void SecondlargestinthearrayUsingSort(int arr[], int n) {
        Arrays.sort(arr);
        int largest = arr[n - 1];
        int Secondlargest = -1;

        for (int i = arr.length - 2; i >= 0; i--) {
            if (arr[i] < largest) {
                Secondlargest = arr[i];
                break;
            }
        }
        System.out.println("Second-largest element using sorting: " + Secondlargest);
    }

    // Method to find the second-largest element using two-pass linear search
    public static void SecondlargestinthearrayUsingLargest(int arr[], int n) {
        int largest = arr[0];
        int Secondlargest = -1;

        // First pass to find the largest element
        for (int i = 0; i < n; i++) {
            if (arr[i] > largest) {
                largest = arr[i];
            }
        }

        // Second pass to find the second-largest element
        for (int i = 0; i < n; i++) {
            if (arr[i] > Secondlargest && arr[i] != largest) {
                Secondlargest = arr[i];
            }
        }
        System.out.println("Second-largest element using largest: " + Secondlargest);
    }

    // Method to find the second-largest element using a single traversal
    public static void SecondlargestinthearrayUsingArray(int arr[], int n) {
        int largest = arr[0];
        int Secondlargest = -1;

        for (int i = 1; i < n; i++) {
            if (arr[i] > largest) {
                Secondlargest = largest;
                largest = arr[i];
            } else if (arr[i] < largest && arr[i] > Secondlargest) {
                Secondlargest = arr[i];
            }
        }
        System.out.println("Second-largest element using single traversal: " + Secondlargest);
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        
        System.out.println("Enter the number of elements: ");
        int n = sc.nextInt();
        
        int[] arr = new int[n];
        System.out.println("Enter " + n + " elements: ");
        for (int i = 0; i < n; i++) {
            arr[i] = sc.nextInt();
        }

        printarr(arr);

        // Finding second-largest using different methods
        SecondlargestinthearrayUsingSort(arr, n);
        SecondlargestinthearrayUsingLargest(arr, n);
        SecondlargestinthearrayUsingArray(arr, n);
    }
}
```



## Overview

This Java program finds the second-largest element from an array using three different approaches:
1. **Using sorting**: The array is sorted, and the second-largest element is found by traversing backwards from the largest.
2. **Using linear search**: The largest element is first found, and then the second-largest is determined by a second pass through the array.
3. **Using a single traversal**: The second-largest element is found in one pass while simultaneously keeping track of the largest.

## Functionality

### Input:
- The program takes the number of elements (`n`) and the `n` integers as input from the user.

### Output:
- The program displays the array entered by the user.
- It then prints the second-largest element of the array using:
  1. Sorting
  2. Two-pass search (finding the largest first)
  3. Single traversal

## Methods

### 1. `printarr(int[] arr)`
This method prints the elements of the array.

**Parameters**: `int[] arr` - the array to be printed.

### 2. `SecondlargestinthearrayUsingSort(int[] arr, int n)`
This method sorts the array and returns the second-largest element by traversing from the second last element (just before the largest).

**Steps**:
- Sorts the array using `Arrays.sort()`.
- Traverses from the second last element, comparing with the largest.

**Time Complexity**: 
- Sorting an array using the `Arrays.sort()` method has a **time complexity of O(n log n)** where `n` is the number of elements in the array.

### 3. `SecondlargestinthearrayUsingLargest(int[] arr, int n)`
This method finds the largest element first, and then iterates again to find the second-largest element.

**Steps**:
- The first loop finds the largest element.
- The second loop finds the second-largest by skipping the largest element.

**Time Complexity**: 
- **O(n)** for two passes through the array.

### 4. `SecondlargestinthearrayUsingArray(int[] arr, int n)`
This method finds the second-largest element in one traversal while keeping track of both the largest and the second-largest elements.

**Steps**:
- Initialize the largest and second-largest elements.
- Traverse the array once, updating both variables as needed.

**Time Complexity**: 
- **O(n)** for a single pass through the array.

### Main Method
- Takes input from the user for the number of elements and the elements of the array.
- Calls the `printarr` method to display the array.
- Calls all three methods to display the second-largest element found through each approach.

## Example Run:

```
Enter the number of elements: 6
Enter 6 elements:
12 45 23 67 34 67
12 45 23 67 34 67
Second-largest element using sorting: 45
Second-largest element using largest: 45
Second-largest element using single traversal: 45
```

## Time Complexity:

| Method                                         | Time Complexity   |
|------------------------------------------------|-------------------|
| `SecondlargestinthearrayUsingSort()`            | O(n log n)        |
| `SecondlargestinthearrayUsingLargest()`         | O(n)              |
| `SecondlargestinthearrayUsingArray()`           | O(n)              |

## Conclusion
- **Sorting** is useful when you need ordering but is less efficient for simply finding the second-largest element due to the O(n log n) complexity.
- **Two-pass linear search** works well with a time complexity of O(n).
- **Single traversal** is the most efficient, finding the second-largest in just O(n) with only one pass.

This program demonstrates multiple ways of solving the problem of finding the second-largest element in an array, with different time complexities.

