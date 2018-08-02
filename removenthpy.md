# Practice
删除链表的倒数第N个节点
## 问题分析：
#### 
给定一个链表，删除链表的倒数第 n 个节点，并且返回链表的头结点。
## 说明
给定的 n 保证是有效的。
## 编程实现：
```Python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def removeNthFromEnd(self, head, n):
        """
        :type head: ListNode
        :type n: int
        :rtype: ListNode
        """
        List = []  
        count = 0  
        while(head):  ##用列表来做
            List.append(head)  ##添加元素进队列。
            head=head.next  ##元素+1
            count = count+1   ##计数+1
        if count==1:  
            return None  
        if List[-n].next==None:  
            List[-n-1].next = None  
            return List[0]  
        else:  
            List[-n].val = List[-n].next.val  
            List[-n].next = List[-n].next.next  
        return List[0]   
```
## 总结体会：
解释里也解释了一部分，这是加入了列表的做法，如果有对应的元素符合条件，把其拿出列表，最后保证输出即可。