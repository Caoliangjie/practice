# Practice
根据二叉树创建字符串
## 问题分析：
#### 
你需要采用前序遍历的方式，将一个二叉树转换成一个由括号和整数组成的字符串。

空节点则用一对空括号 "()" 表示。而且你需要省略所有不影响字符串与原始二叉树之间的一对一映射关系的空括号对。
## 示例 1:
### 输入:
 二叉树: [1,2,3,4]
### 输出:
 "1(2(4))(3)"
### 解释:
 原本将是“1(2(4)())(3())”，
在你省略所有不必要的空括号对之后，
它将是“1(2(4))(3)”。
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
    string tree2str(TreeNode* t) {
        if(t == NULL) {
            return "";
        }
        string str = to_string(t->val);
        if(t->left != NULL) {
            str+='('+tree2str(t->left)+')';
        }
        else if(t->right!= NULL) {
            str += "()";
        }

        if(t->right!= NULL) {
            str+='('+tree2str(t->right)+')';
        }
        return str;
    }
};
```
## 总结体会：
第一个例子说根节点1有左右两个子节点2和3，点2有左子节点4，而输出的字符串为”1(2(4))(3)”。这说明当某个节点左右两个子节点均不为空时，应加上()，并在其中加上子节点的值；而当某个节点只存在左子节点时，则可以省略右子节点对应的()。 那么采用先序遍历的方法就可以了，在遍历的时候我们只要注意判断左右子节点是否为空，就可以顺利解决这个问题。
