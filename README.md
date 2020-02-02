# Binary Tree Paths
## https://leetcode.com/problems/binary-tree-paths

Given a binary tree, return all root-to-leaf paths.

Note: A leaf is a node with no children.

```
Example:

Input:

   1
 /   \
2     3
 \
  5

Output: ["1->2->5", "1->3"]

Explanation: All root-to-leaf paths are: 1->2->5, 1->3
````

# Implementation :

```java
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode(int x) { val = x; }
 * }
 */
class Solution {
    public List<String> binaryTreePaths(TreeNode root) {
        List<String> result = new ArrayList<>();
        if(root == null){
            return result;
        }
        dfs(root,"",result);
        return result;    
    }
    
    public void dfs(TreeNode node, String path, List<String> paths){
        path += node.val;
        if(node.left == null && node.right == null){
            paths.add(path);
            return;
        }
        if(node.left != null){
            dfs(node.left, path + "->", paths);
        }
        if(node.right != null){
            dfs(node.right, path + "->", paths);
        }
    }
}
```

# References :
https://www.youtube.com/watch?v=xqS8dyexaNM
