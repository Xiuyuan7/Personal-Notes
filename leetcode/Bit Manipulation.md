## The Number of Bit Sets of an Integer

The number of 1s in the binary representation of an integer.

```java
class Solution {
    public int countSetBits(int n) {
        int count = 0;
        while (n > 0) {
            // check if the last bit is 1
            count += n & 1;
            
            // right shift 1
            n >>= 1;
        }
        return count;
    }
}
```

