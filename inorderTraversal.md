# Practice
中序遍历二叉树
## 问题分析：
#### 
给定一个二叉树，返回它的中序 遍历

## 进阶:
递归算法很简单，你可以通过迭代算法完成吗？
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
    vector<int> inorderTraversal(TreeNode* root) {
        vector<int> v;
        TreeNode* c=root;
           while(c)
           {if (c->left) {
               TreeNode* c1=c->left;
               while((c1->right) && (c1->right!=c))
                c1=c1->right;
               if(!c1->right)
               {
                c1->right=c;
                c=c->left;
               }
               else
               {
                   c1->right=NULL;
                   v.push_back(c->val);
                   c=c->right;
               }
           }
            else
            {
                v.push_back(c->val);
                c=c->right;
            }
           }
        return v;
    }
}; 
```
## 总结体会：
这个和前序遍历就只差一行代码。做法也是用的迭代，主要是把左子树先输出，之后返回根节点再往下进行。如果没有左子树的话，把根节点值置入容器，然后接着从右子树开始找。
