# Shifting Zeros to the Right in an Array

In this blog post, we will discuss how to shift all the zeros in an array to the rightmost side without affecting the order of non-zero elements. This is a common problem in data manipulation and can be efficiently solved using a simple algorithm.

## Problem Statement

Given an array, we need to move all the zeros to the end of the array while maintaining the order of non-zero elements.

### Example

**Input:** `[5, 6, 0, 4, 6, 0, 9, 0, 8]`

**Output:** `[5, 6, 4, 6, 9, 8, 0, 0, 0]`

## Approach

The optimal approach to solve this problem is to use two pointers. One pointer will traverse the array, and the other will keep track of the position to place the next non-zero element.

### Algorithm

1. Initialize two pointers: `i` for traversing the array and `j` to track the next position to place a non-zero element.
2. Traverse the array with the `i` pointer:
   - If `arr[i]` is non-zero, swap `arr[i]` with `arr[j]` and increment `j`.
3. By the end of the traversal, all non-zero elements are shifted to the left, and all zeros are shifted to the right.

### Implementation

Here is the C++ code to implement this approach:

```cpp
#include <bits/stdc++.h>
using namespace std;

void move_zeros_to_right(vector<int>& arr) {
    int j = 0; // Points to the next position to place a non-zero element
    for (int i = 0; i < arr.size(); i++) {
        if (arr[i] != 0) {
            swap(arr[j++], arr[i]);
        }
    }
}

int main() {
    vector<int> arr{5, 6, 0, 4, 6, 0, 9, 0, 8};
    move_zeros_to_right(arr);
    for (int i = 0; i < arr.size(); i++) {
        cout << arr[i] << " ";
    }
    return 0;
}
```

### Explanation

1. We start with two pointers, `i` and `j`, both initialized to 0.
2. As we iterate through the array with `i`:
   - If the current element `arr[i]` is non-zero, we swap it with the element at index `j` and increment `j`.
3. After the loop, all non-zero elements are shifted to the left, and all zeros are at the rightmost side of the array.

### Time Complexity

The time complexity of this algorithm is O(n), where n is the number of elements in the array. This is because we only make one pass through the array.

### Space Complexity

The space complexity is O(1) since we are using a constant amount of extra space.

## Conclusion

In this post, we discussed an efficient way to move all zeros in an array to the end while maintaining the order of non-zero elements. This algorithm is optimal with a time complexity of O(n) and space complexity of O(1). Such problems are common in data manipulation tasks and understanding this technique is useful for tackling similar challenges.

Feel free to try the code and test it with different input arrays to see how it works in practice.

Happy Coding!
