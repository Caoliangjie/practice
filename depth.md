# Practice
二叉树的最大深度
## 问题分析：
#### 
给定一个二叉树，找出其最大深度。
二叉树的深度为根节点到最远叶子节点的最长路径上的节点数
## 说明: 
叶子节点是指没有子节点的节点。
## 编程实现：
```C++
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode(int x) : val(x), left(NULL), right(NULL) {}
 * };
 */
class Solution {
public:
    int maxDepth(TreeNode* root) {
        int a=0;
        if (root!=NULL) {
            a++;
            int a_left=maxDepth(root->left);
            int a_right= maxDepth(root->right);

            a+=a_left>a_right?max_left:max_right;
        }
        return max;
    }
};
```
## 总结体会：
树分为左子树和右子树两部分，我们用递归的做法找到左右子树中深度最大的一棵，这就是该树结构的深度切是最大深度。