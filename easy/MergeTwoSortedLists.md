# 问题
合并两个排好序的链表，并返回新链表。新链表由两个链表的头部拼接而成。
# 代码
```c
ListNode* mergeTwoLists(ListNode* l1, ListNode* l2)
{
    if(l1==NULL) return l2;
    if(l2==NULL) return l1;
    if(l1->val > l2->val)
    {
        ListNode * tmp=l2;
        tmp->next=mergeTwoLists(l1,l2->next);
        return tmp;
    }
    else
    {
        ListNode * tmp=l1;
        tmp->next=mergeTwoList(l1->next,l2);
        return tmp;
    }
}
```
# 总结
此处合并的链表顺序由小到大。采用地柜的方式进行比较
