1. Create a helper to distinguish if two nodes are the same or not.
    - If one of the nodes is null, there are three possible conditions:
      - t1 and t2 are both null (the result will be True)
      - Either t1 or t2 is null (the result will be false)
      So we can easily use "return t1 == t2" to distinguish if they are both null or not
    - Then we just need to compare every value of the pair nodes, and go down until whole tree are traversed.
  ```java
    public boolean helper(TreeNode t1, TreeNode t2){
        if(t1 == null || t2 == null)    return t1 == t2;
        
        return t1.val == t2.val && helper(t1.left, t2.right) && helper(t1.right, t2.left);
    }
  ```
  
    
2. First find if root is null or not, and go down to the left and right child.
```java
    public boolean isSymmetric(TreeNode root) {
        return root == null || helper(root.left, root.right);
    }
```