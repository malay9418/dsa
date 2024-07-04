# Find the largest three distinct elements in an array
### Given an array with all distinct elements, find the largest three elements.

<b>Examples :</b>

```text
Input: arr[] = {10, 4, 3, 50, 23, 90}
Output: 90, 50, 23

Input: arr[] = { 6, 8, 1, 9, 2, 1, 10, 10}
Output: 10, 10, 9
```
<b>Solution :</b>
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
        
      }else if(arrItem > second && arrItem != first) {
        
        third = second;
        second = arrItem;
        
      }else if(arrItem > third && arrItem != first && arrItem != second) {
        
        third = arrItem;
        
      }
    }
    
    cout << first << endl;
    cout << second << endl;
    cout << third << endl;
    
    
    return 0; 
}
```
