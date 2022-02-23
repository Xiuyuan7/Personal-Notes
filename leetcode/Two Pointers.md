# 3Sum (15)

```java
class Solution {
    public List<List<Integer>> threeSum(int[] nums) {
        List<List<Integer>> res = new ArrayList<>();
        Arrays.sort(nums);
        for (int i = 0; i < nums.length; i++) {
            
            // i去重
            if (i > 0 && nums[i] == nums[i - 1]) continue;
            
            int left = i + 1;
            int right = nums.length - 1;
            while (left < right) {
                int sum = nums[i] + nums[left] + nums[right];
                if (sum < 0) left++;
                else if (sum > 0) right--;
                else {
                    res.add(Arrays.asList(nums[i], nums[left], nums[right]));
                    
                    // 去重逻辑应该放在找到一个三元组之后，left去重，right去重
                    while (left < right && nums[left] == nums[left + 1]) left++;
                    while (left < right && nums[right - 1] == nums[right]) right--;
                    
                    // 找到答案时，双指针同时收缩
                    left++;
                    right--;
                }
            }
        }
        return res;
    }
}
```

# 4Sum (18)

```java
class Solution {
    public List<List<Integer>> fourSum(int[] nums, int target) {
        List<List<Integer>> res = new ArrayList<>();
        Arrays.sort(nums);
        for (int i = 0; i < nums.length; i++) {
            
            // i去重
            if (i > 0 && nums[i] == nums[i - 1]) continue;
            
            for (int j = i + 1; j < nums.length; j++) {
                
                // j去重
                if (j > i + 1 && nums[j] == nums[j - 1]) continue;
                
                int left = j + 1;
                int right = nums.length - 1;
                while (left < right) {
                    int sum = nums[i] + nums[j] + nums[left] + nums[right];
                    if (sum < target) left++;
                    else if (sum > target) right--;
                    else {
                        res.add(Arrays.asList(nums[i], nums[j], nums[left], nums[right]));
                        
                        // left，right去重
                        while (left < right && nums[left] == nums[left + 1]) left++;
                        while (left < right && nums[right - 1] == nums[right]) right--;
                        
                        // 找到答案时，双指针同时收缩
                        left++;
                        right--;
                    }
                }
            }
        }
        return res;
    }
}
```

