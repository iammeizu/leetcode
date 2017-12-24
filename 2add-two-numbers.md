## 2.Add Two Numbers

解题思路：

python中的单链表的问题不像C++这么繁琐

分别遍历两个链表，相加所指向的两个元素，记录进位，直到遍历到其中一个链表的末尾

注意解决边界条件

```
 # Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None
class Solution:
    def addTwoNumbers(self, l1, l2):
        sum = []
        s = 0
        c = 0
        if l1 == None:
            return l2
        if l2 == None:
            return l1
            
        while l1 != None and l2 != None:
            s = l1.val + l2.val + c
            sum.append(s % 10)
            c = int(s / 10)
            l1 = l1.next
            l2 = l2.next
            
        while l1 != None:
            s = l1.val + c
            sum.append(s % 10)
            c = int(s / 10)
            l1 = l1.next
        
        while l2 != None:
            s = l2.val + c
            sum.append(s % 10)
            c = int(s / 10)
            l2 = l2.next
        
        if c > 0:
            sum.append(c)
        return sum
```

代码逻辑比较简单易懂

