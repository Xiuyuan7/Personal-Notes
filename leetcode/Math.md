# Prime Factors of an Integer

Given a number **n**, write an efficient function to print all prime factorsof **n**.

```java
class Solution {
    public List<Integer> primeFactors(int n) {
        List <Integer> res = new ArrayList<>();
        
        // print the number of 2s that divide n
        while (n % 2 == 0) {
            res.add(2);
            n /= 2;
        }
        
        // n must be odd at this point.
        for (int i = 3; i < Math.sqrt(n); i += 2) {
            
            // While i divides n, print i and divide n
            while (n % i == 0) {
                res.add(i);
                n /= i;
            }
            
        }
        
        // handle the case when n is a prime number greater than 2
        if (n > 2) res.add(n);
        
        return res;
    }
}
```

