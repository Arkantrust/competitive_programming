# 191. Number of 1 Bits

[Leetcode](https://leetcode.com/problems/number-of-1-bits/)

```cpp
class Solution {
public:
    int hammingWeight(int n) {

        int setBits = 0;

        while (n != 0) {
        
            if (n % 2 != 0)
                setBits++;

            n /= 2;
        
        }

        return setBits;
    
    }
};
```
