# Practice
合并二叉树
## 问题分析：
#### 
给定两个二叉树，想象当你将它们中的一个覆盖到另一个上时，两个二叉树的一些节点便会重叠。

你需要将他们合并为一个新的二叉树。合并的规则是如果两个节点重叠，那么将他们的值相加作为节点合并后的新值，否则不为 NULL 的节点将直接作为新二叉树的节点。
### 注意: 
合并必须从两个树的根节点开始。

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
    TreeNode* mergeTrees(TreeNode* t1, TreeNode* t2) {
        if(t1&&t2){                                 
            t1->val+=t2->val;                            
            t1->left=mergeTrees(t1->left,t2->left);   
            t1->right=mergeTrees(t1->right,t2->right);
            return t1;                               
        }
        else if(!t1&&t2){                          
            return t2;
        }
        else if(!t1&&!t2){                       
            return NULL;
        }
        else{                                     
            return t1;
        }
    }
};
```
## 总结体会：
从两个树的根节点开始，对于t1和t2，如果t1和t2都不是空结点，那么求结点值的和放到t1中，如果只有t2结点不空，那么返回t2结点。如果两结点都为空，那么返回NULL。最后统一返回到t1。