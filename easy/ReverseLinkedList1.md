# 问题
将一个链表进行翻转。
# 代码
```c
ListNode* reverseList(ListNode* head)
{
  ListNode* prev = nullptr;
  ListNode* curr = head;
  ListNode* next;
  while (curr)
   {
      next = curr->next;
      curr->next = prev;
      prev = curr;
      curr = next;
   }  
   return prev;
}
```
# 总结
注意链表的最后一项指向null.
