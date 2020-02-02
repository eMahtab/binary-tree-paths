# Binary Tree Paths
## 


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
