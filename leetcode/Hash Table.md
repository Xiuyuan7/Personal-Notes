1. array
2. hashset
3. hashmap

# Valid Anagram (242)

```java
class Solution {
    public boolean isAnagram(String s, String t) {
        int[] record = new int[26];
        for (char c : s.toCharArray()) {
            record[c - 'a'] += 1;
        }
        for (char c : t.toCharArray()) {
            record[c - 'a'] -= 1;
        }
        for (int n : record) {
            if (n != 0) return false;
        }
        return true;
    }
}
```

Time complexity: O(n)

Space complexity: O(1)

# Find Common Characters (1002)

```java
class Solution {
    public List<String> commonChars(String[] words) {
        List<String> res = new ArrayList<>();
        if (words.length == 0) return res;
        
        // record the minimum occurances of a character in all words.
        int[] minRecord = new int[26];
        
        // initiate minRecord
        for (char c : words[0].toCharArray()) {
            minRecord[c - 'a']++;
        }
        
        // loop through each word
        for (String s : words) {
            
            // record the number of each character's occurances in a word
            int[] record = new int[26];
            for (char c : s.toCharArray()) {
                record[c - 'a']++;
            }
            
            // update minRecord and record the minimum occurances
            for (int i = 0; i < 26; i++) {
                minRecord[i] = Math.min(minRecord[i], record[i]);
            }
        }
        
        // convert the record to output strings
        for (int i = 0; i < 26; i++) {
            while (minRecord[i] != 0) {
                char c = (char) (i + 'a');
                res.add(String.valueOf(c));
                minRecord[i]--;
            }
        }
        return res;
    }
}
```

# Intersection of Two Arrays (349)

 ```java
 class Solution {
     public int[] intersection(int[] nums1, int[] nums2) {
         
         // handle corner conditions
         if (nums1 == null || nums1.length == 0 || nums2 == null || nums2.length == 0 {
             return new int[0];
         }
         
         Set<Integer> set = new HashSet<>();
         Set<Integer> resSet = new HashSet<>();
         
         // check intersection
         for (int n : nums1) {
             set.add(n);
         }
         
         for (int n : nums2) {
             if (set.contains(n)) {
                 resSet.add(n);
             }
         }
         
         // convert set to array
         int[] res = new int[resSet.size()];
         int index = 0;
         for (int n : resSet) {
             res[index++] = n;
         }
             
         return res;
     }
 }
 ```

# Happy Number (202)

```java
class Solution {
    public boolean isHappy(int n) {
        Set<Integer> set = new HashSet<>();
        while (n != 1 && !set.contains(n)) {
            set.add(n);
            n = getSum(n);
        }
        return n == 1;
    }
    
    // get the sum of the squares of a positive integer's digits
    public int getSum(int n) {
        int sum = 0;
        while (n > 0) {
            int digit = n % 10;
            sum += digit * digit;
            n /= 10;
        }
        return sum;
    }
}
```

# Two Sum (1)

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        int[] res = new int[2];
        if (nums == null || nums.length == 0) return res;
        Map<Integer, Integer> map = new HashMap<>();
        for (int i = 0; i < nums.length; i++) {
            int temp = target - nums[i];
            
            // check if temp is in the map
            if (map.containsKey(temp)) {
                res[0] = i;
                res[1] = map.get(temp);
            }
            map.put(nums[i], i);
        }
        return res;
    }
}
```

# 4Sum II (454)

```java
class Solution {
    public int fourSumCount(int[] nums1, int[] nums2, int[] nums3, int[] nums4) {
        int res = 0;
        
        // key: sum of n1 and n2; value: the number of occurances of the sum
        Map<Integer, Integer> map = new HashMap<>();
        for (int n1 : nums1) {
            for (int n2 : nums2) {
                int temp = n1 + n2;
                if (map.containsKey(temp)) map.put(temp, map.get(temp) + 1);
                else map.put(temp, 1);
            }
        }
        
        for (int n3 : nums3) {
            for (int n4 : nums4) {
                int temp = n3 + n4;
                if (map.containsKey(0 - temp)) res += map.get(0 - temp);
            }
        }
        
        return res;
    }
}
```

# Ransom Note (383)

```java
class Solution {
    public boolean canConstruct(String ransomNote, String magazine) {
        int[] record = new int[26];
        for (char c : magazine.toCharArray()) {
            record[c - 'a']++;
        }
        for (char c : ransomNote.toCharArray()) {
            record[c - 'a']--;
        }
        for (int n : record) {
            if (n < 0) return false;
        }
        return true;
    }
}
```



