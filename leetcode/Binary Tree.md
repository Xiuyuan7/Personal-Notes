# 108 Convert Sorted Array to Binary Search Tree

Recursion

```java
class Solution {
    public TreeNode sortedArrayToBST(int[] nums) {
        TreeNode root = traversal(nums, 0, nums.length - 1);
        return root;
    }
    public TreeNode traversal(int[] nums, int left, int right) {
        if (left > right) return null;
        int mid = left + ((right - left) / 2);
        TreeNode root = new TreeNode(nums[mid]);
        root.left = traversal(nums, l, mid - 1);
        root.right = traversal(nums, mid + 1, right);
        return root;
    }
}
```



# 700 Search in a Binary Search Tree

Recursion

```java
class Solution {
    public TreeNode searchBST(TreeNode root, int val) {
        if (root == null || root.val == val) return root;
        if (root.val < val) return searchBST(root.right, val);
        else return searchBST(root.left, val);
    }
}
```

