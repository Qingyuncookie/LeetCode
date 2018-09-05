# 问题
给定两个排好序的链表，合并为一个链表，由两个链表剪接得到。
# 代码
```python
class Solution(object)
      def mergeTwoLists(self, l1, l2):
          if not l1 or l2:
            return l1 or l2
          head = cur = ListNode(0)
          while l1 and l2:
            if l1.val < l2.val
                cur.next = l1
                l1 = l1.next
            else:
                cur.next = l2
                l2 = l2.next
            cur = cur.next
         cur.next = l1 or l2
         return head.next                
```
# 总结
合并后的链表仍然是有序的，可以同时遍历两个链表，每次选取两个链表中较小值的节点，依次连接起来，就能得到最终的链表。 
