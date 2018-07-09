# Practice
二叉树的前序遍历
## 问题分析：
#### 
给定一个二叉树，返回它的 前序 遍历。
###  进阶
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
    vector<int> preorderTraversal(TreeNode* root) {
        vector<int> v;
        TreeNode* c=root;
           while(c)
           {if (c->left) {//判断是不是有左结点。
               TreeNode* c1=c->left;
               while((c1->right) && (c1->right!=c))
                c1=c1->right;
               if(!c1->right)
               {v.push_back(c->val);
                c1->right=c;
                c=c->left;
               }//不是右子树，把该结点数遍历完后置入容器，然后转到右子树上。
               else
               {
                   c1->right=NULL;
                   c=c->right;
               }
           }
            else
            {//没有左子树，根节点弄完后接着换到右边。
                v.push_back(c->val);
                c=c->right;
            }
           }
        return v;
    }
};
```
## 总结体会：
基本的思路在注释里也写到，这边就是不断判断指针指向哪里，按照先走根，再走左子树，再右子树的顺序。每一次把权值紧接着置入容器中，指针位置时刻在变化。这里设置c是为了作为中转，没有左子树可以随时返回接着去找右边是否存在。