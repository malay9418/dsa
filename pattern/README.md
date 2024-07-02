# Number Pattern Problem

## Problem Statement

Given an integer \( N = 6\), print the following pattern:

```
6 6 6 6 6 6 6 6 6 6 6 
6 5 5 5 5 5 5 5 5 5 6 
6 5 4 4 4 4 4 4 4 5 6 
6 5 4 3 3 3 3 3 4 5 6 
6 5 4 3 2 2 2 3 4 5 6 
6 5 4 3 2 1 2 3 4 5 6 
6 5 4 3 2 2 2 3 4 5 6 
6 5 4 3 3 3 3 3 4 5 6 
6 5 4 4 4 4 4 4 4 5 6 
6 5 5 5 5 5 5 5 5 5 6 
6 6 6 6 6 6 6 6 6 6 6
```

## Solution

```cpp
#include <iostream>
using namespace std;

int main() 
{
    int N;
    cin >> N;
    
    for(int i = 1; i <= 2 * N - 1; i++) {
      
      int startValue = N;
      int iInverted = 2 * N - i;
      
      for(int j = 1; j <= 2 * N - 1; j++) {
        if(i <= N) {
          cout << startValue;
          int lowerLimit = i;
          int upperLimit = 2 * N - i - 1;
           
          if(j < lowerLimit) {
            startValue--;
          }else if(j > upperLimit) {
            startValue++;
          }
          
        }else {
          cout << startValue;
          int lowerLimit = iInverted;
          int upperLimit = 2 * N - iInverted - 1;
           
          if(j < lowerLimit) {
            startValue--;
          }else if(j > upperLimit) {
            startValue++;
          }
          
        }
        
        cout << "  ";
      }
      
      cout << endl;
    }
    
    return 0;
}
```
