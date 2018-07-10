# Practice
删除链表中的节点
## 问题分析：
#### 
请编写一个函数，使其可以删除某个链表中给定的（非末尾）节点，你将只被给定要求被删除的节点。
### 说明:
    链表至少包含两个节点。
    链表中所有节点的值都是唯一的。
    给定的节点为非末尾节点并且一定是链表中的一个有效节点。
    不要从你的函数中返回任何结果。
## 编程实现：
```C++
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution {
public:
    void deleteNode(ListNode* node) {
        node->val = node->next->val;
        node->next = node->next->next;}//只关注这一个点的话，这里一定是个有效节点前提下把node中val值传递给下一个节点，再把指针指向下个节点即可将这一个节点消除。
};
```
## 总结体会：
可以说是最简单的一个链表操作，如果保证在这个节点有效的话，让该点的val等于next的val，该next指针再指向下一个next的next即可保证这个元素不存在了。