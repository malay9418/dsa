# Number Pattern Problem

## Problem Statement

Given an integer \( N = 6 \), print the following pattern:

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

## Java Solution

```java
public class NumberPattern {
    public static void main(String[] args) {
        int N = 6;
        for (int i = 1; i <= 2 * N - 1; i++) {
            int startValue = N;
            int iInverted = 2 * N - i;
            
            for (int j = 1; j <= 2 * N - 1; j++) {
                if (i <= N) {
                    System.out.print(startValue + " ");
                    int lowerLimit = i;
                    int upperLimit = 2 * N - i - 1;
                    
                    if (j < lowerLimit) {
                        startValue--;
                    } else if (j > upperLimit) {
                        startValue++;
                    }
                } else {
                    System.out.print(startValue + " ");
                    int lowerLimit = iInverted;
                    int upperLimit = 2 * N - iInverted - 1;
                    
                    if (j < lowerLimit) {
                        startValue--;
                    } else if (j > upperLimit) {
                        startValue++;
                    }
                }
            }
            System.out.println();
        }
    }
}
```

## Python Solution

```python
def number_pattern(N):
    for i in range(1, 2 * N):
        start_value = N
        i_inverted = 2 * N - i
        
        for j in range(1, 2 * N):
            if i <= N:
                print(start_value, end=" ")
                lower_limit = i
                upper_limit = 2 * N - i - 1
                
                if j < lower_limit:
                    start_value -= 1
                elif j > upper_limit:
                    start_value += 1
            else:
                print(start_value, end=" ")
                lower_limit = i_inverted
                upper_limit = 2 * N - i_inverted - 1
                
                if j < lower_limit:
                    start_value -= 1
                elif j > upper_limit:
                    start_value += 1
        print()

number_pattern(6)
```

## C++ Solution

```cpp
#include <iostream>
using namespace std;

int main() 
{
    int N = 6;
    
    for(int i = 1; i <= 2 * N - 1; i++) {
        int startValue = N;
        int iInverted = 2 * N - i;
        
        for(int j = 1; j <= 2 * N - 1; j++) {
            if(i <= N) {
                cout << startValue << " ";
                int lowerLimit = i;
                int upperLimit = 2 * N - i - 1;
                
                if(j < lowerLimit) {
                    startValue--;
                } else if(j > upperLimit) {
                    startValue++;
                }
            } else {
                cout << startValue << " ";
                int lowerLimit = iInverted;
                int upperLimit = 2 * N - iInverted - 1;
                
                if(j < lowerLimit) {
                    startValue--;
                } else if(j > upperLimit) {
                    startValue++;
                }
            }
        }
        cout << endl;
    }
    
    return 0;
}
```
