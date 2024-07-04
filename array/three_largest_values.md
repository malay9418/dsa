# Finding the Largest Three Distinct Elements in an Array

## Problem Statement
Given an array with all distinct elements, find the largest three elements.

**Examples:**

- **Input:** `arr[] = {10, 4, 3, 50, 23, 90}`
  - **Output:** `90, 50, 23`

- **Input:** `arr[] = {6, 8, 1, 9, 2, 1, 10, 10}`
  - **Output:** `10, 10, 9`

## Solution Explanation

### Visual Representation

![Visual Representation](placeholder_image_1)

### Step-by-Step Explanation

1. **Initialization:**
   - Initialize three variables `first`, `second`, and `third` to `INT_MIN` to ensure they can be replaced by any element in the array.

    ```cpp
    int first = INT_MIN;
    int second = INT_MIN;
    int third = INT_MIN;
    ```

    ![Initialization](placeholder_image_2)

2. **Iteration Through the Array:**
   - Iterate through each element in the array to determine its position relative to the current `first`, `second`, and `third` largest elements.

    ```cpp
    for (int i = 0; i < n; i++) {
        int arrItem = arr[i];
        ...
    }
    ```

    ![Iteration](placeholder_image_3)

3. **Comparison and Placement:**
   - **If the current element is greater than `first`:**
     - Shift the current values of `first`, `second`, and `third` down by one position.
     - Assign the current element to `first`.

     ```cpp
     if (arrItem > first) {
         third = second;
         second = first;
         first = arrItem;
     }
     ```

     ![First Check](placeholder_image_4)

   - **If the current element is greater than `second` and not equal to `first`:**
     - Shift the current values of `second` and `third` down by one position.
     - Assign the current element to `second`.

     ```cpp
     else if (arrItem > second && arrItem != first) {
         third = second;
         second = arrItem;
     }
     ```

     ![Second Check](placeholder_image_5)

   - **If the current element is greater than `third` and not equal to `first` and `second`:**
     - Assign the current element to `third`.

     ```cpp
     else if (arrItem > third && arrItem != first && arrItem != second) {
         third = arrItem;
     }
     ```

     ![Third Check](placeholder_image_6)

### Example Walkthrough

Given `arr[] = {10, 4, 3, 50, 23, 90}`:

- **Initialization:**

  ```cpp
  first = INT_MIN
  second = INT_MIN
  third = INT_MIN
  ```

  ![Initialization Example](placeholder_image_7)

- **Processing each element:**

  - For `10`:

    ```cpp
    first = 10, second = INT_MIN, third = INT_MIN
    ```

    ![First Element](placeholder_image_8)

  - For `4`:

    ```cpp
    first = 10, second = 4, third = INT_MIN
    ```

    ![Second Element](placeholder_image_9)

  - For `3`:

    ```cpp
    first = 10, second = 4, third = 3
    ```

    ![Third Element](placeholder_image_10)

  - For `50`:

    ```cpp
    first = 50, second = 10, third = 4
    ```

    ![Fourth Element](placeholder_image_11)

  - For `23`:

    ```cpp
    first = 50, second = 23, third = 10
    ```

    ![Fifth Element](placeholder_image_12)

  - For `90`:

    ```cpp
    first = 90, second = 50, third = 23
    ```

    ![Sixth Element](placeholder_image_13)

### Summary
- **First Check:** If greater than `first`, shift all down and assign.
- **Second Check:** If greater than `second` and not equal to `first`, shift `second` and `third` down and assign.
- **Third Check:** If greater than `third` and not equal to `first` and `second`, assign to `third`.

This method ensures we maintain the three largest distinct elements through a single pass over the array.

## Complete Code

```cpp
#include <iostream>
#include <limits.h>
#include <cstdio>
using namespace std;

int main() 
{
    int n;
    scanf("%d", &n);

    int arr[n];
    for (int i = 0; i < n; ++i) {
        scanf("%d", &arr[i]);
    }
    
    int first, second, third;
    first = second = third = INT_MIN;
    
    for(int i = 0; i < n; i ++) {
      int arrItem = arr[i];
      
      if(arrItem > first) {
        third = second;
        second = first;
        first = arrItem;
      } else if(arrItem > second && arrItem != first) {
        third = second;
        second = arrItem;
      } else if(arrItem > third && arrItem != first && arrItem != second) {
        third = arrItem;
      }
    }
    
    cout << first << endl;
    cout << second << endl;
    cout << third << endl;
    
    return 0; 
}
```
