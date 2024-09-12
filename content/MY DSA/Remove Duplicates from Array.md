---
title: Remove Duplicates from Array  
tags:  
  - Remove Duplicates
  - Array Duplicates Removal

---

# Duplicate Finder and Remover in Java


## Code

```java
import java.util.HashSet;
import java.util.Scanner;
import java.util.Set;
import java.util.*;

public class Duplicateinarray {
    public static int findDuplicateinarray(int  [ ] arr){

        HashSet <Integer> set= new HashSet<>();

        for(int i =0 ;i<arr.length;i++){
            set.add(arr[i]);
        }
        int k = set.size();
        int j=0;

        for(int x:set){
            arr[j++]=x;
        }

        return k;
    }

public static void printDuplicatearray(int arr[],int k ){

    for(int i=0;i<k;i++){

        System.out.print(arr[i]);

    }
}

    public static int findDuplicateinarrayusingTwoPointer(int  [ ] arr){
            int i=0;
            for(int j=1;j<arr.length;j++){
                if(arr[j]!=arr[i]){
                    arr[i+1]=arr[j];
                    i++;
                }
            }
        return i+1;
    }

    public static void  main (String [] arg){

        Scanner sc = new Scanner(System.in);

        

        int [ ] ar={1,1,3,4,5};
        
       int  k1= findDuplicateinarray(ar);

        printDuplicatearray(ar,k1);

       int  k2=  findDuplicateinarrayusingTwoPointer(ar);

        printDuplicatearray(ar,k2);

    } 
}

```


## Overview

This Java program finds and removes duplicates from an array using two approaches:
1. **Using a HashSet**: This approach leverages a `HashSet` to filter out duplicates.
2. **Using the Two-Pointer technique**: This approach works on sorted arrays, using two pointers to eliminate duplicates.

## Functionality

### Input:
- The program checks a predefined array of integers that may contain duplicates.

### Output:
- The program prints the array after removing duplicates using:
  1. **HashSet**
  2. **Two-Pointer Technique**

## Methods

### 1. `findDuplicateinarray(int[] arr)`
This method removes duplicates using a `HashSet`.

**Steps**:
- Initialize a `HashSet` to store unique elements.
- Traverse the array, adding each element to the `HashSet`.
- Copy the unique elements from the `HashSet` back to the array.
- Return the number of unique elements.

**Time Complexity**: 
- Adding elements to a `HashSet` takes **O(n)**, and iterating through the array also takes **O(n*log(n))**, so the overall complexity is **O(n*log(n))+O(n)**.

### 2. `findDuplicateinarrayusingTwoPointer(int[] arr)`
This method removes duplicates using a two-pointer technique. It assumes the array is sorted.

**Steps**:
- Initialize two pointers, `i` and `j`. Pointer `i` keeps track of the position of the last unique element, and pointer `j` scans the array for the next unique element.
- If the current element is not equal to the last unique element, move `i` forward and copy the new unique element to its position.
- Return the number of unique elements.

**Time Complexity**: 
- Since each element is processed once, the time complexity is **O(n)**.

### Main Method
- The program defines an array of integers that may contain duplicates.
- It calls both methods to remove duplicates and prints the resulting arrays.

## Example Run:

```
Array: [1, 1, 3, 4, 5]
Using HashSet: 1 3 4 5
Using Two-Pointer: 1 3 4 5
```

## Time Complexity:

| Method                                   | Time Complexity   |
|------------------------------------------|-------------------|
| `findDuplicateinarray()`                 | O(n*log(n))+O(n)  |
| `findDuplicateinarrayusingTwoPointer()`  | O(n)              |

## Conclusion
- **HashSet** is a simple and intuitive approach, but it uses extra space.
- **Two-Pointer** is more space-efficient, but it works only on sorted arrays.
- Both methods offer an efficient time complexity of **O(n)**, making them suitable for large datasets.