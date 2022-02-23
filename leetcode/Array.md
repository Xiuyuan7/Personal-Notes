## 48 Rotate Image

```java
class Solution {
    public void rotate(int[][] matrix) {
        int n = matrix.length;
        for (int i = 0; i < n / 2; i++) {
            for (int j = i; j < n - 1 - i; j++) {
                // save the top
                int tmp = matrix[i][j];
                
                // move left to top
                matrix[i][j] = matrix[n - 1 - j][i];
                
                // move bottom to left
                matrix[n - 1 - j][i] = matrix[n - 1 - i][n - 1 - j];
                
                // move right to bottom
                matrix[n - 1 - i][n - 1 - j] = matrix[j][n - 1 - i];
                
                // m
                matrix[j][n - 1 - i] = tmp;
            }
        }
    }
}
```

