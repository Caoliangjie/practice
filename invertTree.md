# Practice
Invert Binary Tree
## 问题分析：
#### 
Invert a binary tree.
## 编程实现：
```C++
/*
    public class TreeNode
    {
        int val;
        TreeNode left;
        TreeNode right;
        TreeNode(int x)
        { val = x; }
    }
*/
class Solution {
public:
    TreeNode* invertTree(TreeNode* root) {
        if(root==NULL)
            return NULL;
        TreeNode * leftTree=NULL;
        TreeNode * rightTree=NULL;
        if(root->left)
            leftTree=invertTree(root->left);
        if(root->right)
            rightTree=invertTree(root->right);
        root->left=rightTree;
        root->right=leftTree;
        return root;
    }
};

```
## 总结体会：
这里做法比较简便，递归地交换根节点的左右子树。